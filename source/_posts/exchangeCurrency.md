---
title: "환율변환 프로젝트"
author: "Young Jae Kim"
date: '2022-01-26'
output:
  html_document:
    keep_md: true
categories: 
- Development
- 환율계산기
tags:
- Development
- 환율계산기

---
# Exchange Currency Project

### 1. 이 화면을 보고 내가 해야 하는것 .

 1. 나에게는 같은 크기 같은 기능의 exchange box 가 두개 필요하다.

 2. 그리고 그 exchange box 에는  한개의 드랍다운과 2개의 input box 가 있다 . 

 

![Untitled](images/exchangeCurrency/0.png)


### 2. 위에 데모를 보고 깨달은 것을 토대로 index.html 을 구성해준다.

- 먼저 이벤트를 넣어주는 방법은 html 에서 onkeyup 처럼 넣어주는 방법이 있고, main.js 에서 넣어주는 방법이 있다.

![Untitled](images/exchangeCurrency/1.png)

                              **<html 에서 직접적으로 onkeyup 으로 넣어주는 인라인 기법>**

![Untitled](images/exchangeCurrency/2.png)

                            **<main.js 에서 addEventListener 로 이벤트를 넣어주는 기법>**

### 3. 뼈대인 html 이 완성되었으니 main.js 에서 좀더 기능을 상세하게 해주자 .

1. 먼저, 환율을 변경해주기 위해서는, 계속해서 반복적으로 들어가는 정보이고, 연계되는 데이터일때, 객체라는 데이터타입으로 여러가지 정보를 정의해주어, 접근하기 쉽게 해준다. 

```jsx
// 값이 여러가지 정보가 들어가야 할 때 객체라는 데이터타입을 쓴다.
let currencyRatio={
    USD:{
        KRW:1241.00,
        USD:1,
        VND:23450.00,
        unit:"달러",
        img: "https://cdn-icons-png.flaticon.com/512/555/555526.png",
        
    },
    KRW:{
        KRW:1,
        USD:0.00081,
        VND:18.92,
        unit:"원",
        img: "https://cdn.countryflags.com/thumbs/south-korea/flag-400.png",
    },
    VND:{
        VND:1,
        KRW:0.053,
        USD:0.000043,
        unit:"동",
        img: "https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Flag_of_Vietnam.svg/2560px-Flag_of_Vietnam.svg.png",
    }
}
```

1. 이렇게 버튼이 클릭 될 때  그 버튼이 클릭된 나라의 이니셜과 국기가 나오게 코딩을 하여주어야 한다

![GOMCAM 20230124_1403590252.gif](images/exchangeCurrency/3.gif)

     

```jsx

   
document.querySelectorAll("#from-currnecy-list a").forEach((menu)=>menu.addEventListener("click",function(){
    
  
    //2.버튼에 값을 바꾼다. textcontent 선택한 버튼의 텍스트를 들고오는것 내가 선택한 텍스트를 들고와서 이 버튼 텍스트에 넣어준다.
    
    document.getElementById("from-button").textContent=this.textContent
    console.log(document.getElementById("from-button").textContent)
   
    //3.선택된 currency 값을 변수에 저장해준다. 
    //초기값
    selectCurrency=this.textContent;
    
    document.getElementById("from-button").innerHTML=`<img class="flag-img" src=${currencyRatio[selectCurrency].img}>${selectCurrency}`
    console.log("현재 선택 통화는"+selectCurrency);
    convert();

}));
```

**logic**

1. querySelectorAll 로 from-currency-list 의 id를 가진 a 태그 요소들을 다 읽는다. 그런이후, 
2. forEach를 통해서, 각각이 value 들이 클릭 되어질때 함수를 실행시킨다

### 함수내용

1. 함수⇒getElementById 를 통해  id가 from-button 인 텍스트를 뽑은다음에 this에 저장을해둔다.
2.  selectCurrency=this.textContent;  그 선택된 텍스트를 selectCurrency 로 저장을해둔다 .
3. document.getElementById("from-button").innerHTML=`<img class="flag-img" src=${currencyRatio[selectCurrency].img}>${selectCurrency}`  를 통해, 버튼에 노출시켜준다 .

### 4.이제 기껏해봐야 dropdown button 에 선택된 화폐가 오는것 까지 한 것 입니다. 두번째로, convert() 함수를 사용하여 첫번째 inputbox에 환전 amount 를 넣어주었을때 , 계산되어 두번째 박스의 input에 나오게 해주는 작업을 합니다 .

```jsx
function convert(){
     
    let amount=document.getElementById("from-input").value
    commaAmount=amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    let convertedAmount=amount * currencyRatio[selectCurrency][toCurrency]
    let withComma1=convertedAmount.toLocaleString();
    document.getElementById("to-input").value=convertedAmount
    document.getElementById("from-currency").value=commaAmount+currencyRatio[selectCurrency]['unit']
    document.getElementById("to-currency").value=withComma1+currencyRatio[toCurrency]['unit']

}
```

### **logic**

```jsx
let amount=document.getElementById("from-input").value
commaAmount=amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
```

- id=”from-input” 를 가진  input 창의 value 를 가져온다 . ⇒ 우리가 환전할 금액을 input창에 넣으면 그것이 amount에 저장이된다
- commaAmount 는  amount 로 들어간 돈을 정규식을 사용하여 , 3자리마다 쉼표를 찍어주는 역역할을한다.

```jsx
let convertedAmount=amount * currencyRatio[selectCurrency][toCurrency]
```

- convertedAmount 는 입력된 amount 에 미리 객체로 만들어 놓은 [selectCurrency][toCurrency] 에 접근해 환율정보를 가져와 환율을 곱해주어 환액을 저장한다.

```jsx
document.getElementById("to-input").value=convertedAmount
    document.getElementById("from-currency").value=commaAmount+currencyRatio[selectCurrency]['unit']
    document.getElementById("to-currency").value=withComma1+currencyRatio[toCurrency]['unit']
```

- to-input 의 id를 가진 아래의 exchange-box 의 value ( 나타내지는 값) 에 convertedAmount 를 넣어주고 보여지게 한다.
- from-currency  에는 쉼표를 붙힌 commaAmount 와  객체에 접근해주어서 선택된 통화의 단위를 나오게 해준다 .

### Demo 결과물 .

![GOMCAM 20230126_2339000049.gif](images/exchangeCurrency/4.gif)