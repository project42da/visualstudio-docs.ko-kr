---
title: "lbound 메서드(VBArray)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "lbound"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "lbound 메서드"
ms.assetid: 30ff5e8a-8165-494b-bce8-0a562ec2eec3
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# lbound 메서드(VBArray)(JavaScript)
VBArray의 지정된 차원에서 사용하는 최저 인덱스 값을 반환합니다.  
  
## 구문  
  
```  
  
safeArray.lbound(dimension)   
```  
  
## 매개 변수  
 *safeArray*  
 필수 요소.  VBArray 개체입니다.  
  
 `dimension`  
 선택 사항입니다.  하한 인덱스를 구하는 VBArray의 차원입니다.  생략하면 `lbound`는 1이 전달된 것처럼 동작합니다.  
  
## 설명  
 VBArray가 비어 있으면 `lbound` 메서드는 undefined를 반환합니다.  `dimension`이 VBArray의 차원 수보다 크거나 음수이면 메서드는 "범위를 벗어난 첨자" 오류를 발생시킵니다.  
  
## 예제  
 다음 예제는 세 부분으로 구성됩니다.  첫 번째 부분은 Visual Basic 안전 배열을 만들기 위한 VBScript 코드이고  두 번째 부분은 안전 배열의 차원 수와 각 차원의 하한을 결정하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다.  안전 배열은 Visual Basic보다는 VBScript에서 많이 만들기 때문에 하한은 항상 0입니다.  두 부분 모두 HTML 페이지의 \<HEAD\> 섹션에 입력합니다.  세 번째 부분은 \<BODY\> 섹션에 입력하여 다른 두 부분을 실행시키는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다.  
  
```javascript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(j, i) = k  
         k = k + 1  
      Next  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vba){  
   var i;  
   var a = new VBArray(vba);  
   var s = "";  
   for (i = 1; i <= a.dimensions(); i++)  
   {  
      s += "The lower bound of dimension ";  
      s += i + " is ";  
      s += a.lbound(i);  
      s += ".<br />";  
   }  
   return (s);  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
   document.write(VBArrayTest(CreateVBArray()));  
</script>  
</body>  
```  
  
## 요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준에서 지원되고,  [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [VBArray 개체](../../javascript/reference/vbarray-object-javascript.md)  
  
## 참고 항목  
 [dimensions 메서드\(VBArray\)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [getItem 메서드\(VBArray\)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [toArray 메서드\(VBArray\)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [ubound 메서드\(VBArray\)](../../javascript/reference/ubound-method-vbarray-javascript.md)