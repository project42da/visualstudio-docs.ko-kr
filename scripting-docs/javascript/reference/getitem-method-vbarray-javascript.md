---
title: "getItem 메서드 (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getItem
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getItem method
- Item property
ms.assetid: f62964ad-8b2f-4596-95d0-b20e587ecea5
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e6457435d047f2780a19fa8ce26fc2bb86f7ae0e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getitem-method-vbarray-javascript"></a>getItem 메서드(VBArray)(JavaScript)
지정한 위치에 있는 항목을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
safeArray.getItem(dimension1[, dimension2, ...], dimensionN)   
```  
  
## <a name="parameters"></a>매개 변수  
 *safeArray*  
 필수 요소. VBArray 개체입니다.  
  
 *dimension1,..., dimensionN*  
 원하는 VBArray 요소의 정확한 위치를 지정합니다. *n* 은 VBArray의 차원 수와 같습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 세 부분으로 구성됩니다. 첫 번째 부분은 Visual Basic 안전 배열을 만드는 VBScript 코드입니다. 두 번째 부분은 Visual Basic 안전 배열을 반복하고 각 요소의 내용을 출력하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다. 로 이동 하는 두 부분 모두는 \<H e a d > HTML 페이지의 섹션입니다. 세 번째 부분은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에 사용 되는 코드는 \<본문 > 섹션을 두 부분을 실행 합니다.  
  
```JavaScript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(i, j) = k  
         document.writeln(k)  
         k = k + 1  
      Next  
      document.writeln("<BR>")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
<script type="text/javascript">  
<!--  
function GetItemTest(vbarray)  
{  
   var i, j;  
   var a = new VBArray(vbarray);  
   for (i = 0; i <= 2; i++)  
   {  
      for (j =0; j <= 2; j++)  
      {  
         document.writeln(a.getItem(i, j));  
      }  
   }  
}  
-->  
</script>  
</head>  
<body>  
<script type="text/javascript">  
<!--  
   GetItemTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [VBArray Object](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [dimensions 메서드 (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [lbound 메서드 (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [toArray 메서드 (VBArray)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [ubound 메서드(VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)