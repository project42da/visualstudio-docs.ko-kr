---
title: "toArray 메서드 (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- toArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toArray method
ms.assetid: 664de44c-2039-4289-82f6-948e9d744d80
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeee8acad04125eb942089b4d8dacef6f0f5e6fb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="toarray-method-vbarray-javascript"></a>toArray 메서드(VBArray)(JavaScript)
VBArray에서 변환된 표준 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
safeArray.toArray( )   
```  
  
## <a name="remarks"></a>설명  
 필수 *safeArray* 참조는 VBArray 개체입니다.  
  
 변환에서는 다차원 VBArray를 1차원 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열로 변환합니다. 연속된 각 차원이 이전 차원의 끝에 추가됩니다. 예를 들어 3차원 VBArray와 각 차원의 요소 3개가 다음과 같이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열로 변환됩니다.  
  
 VBArray가 (1, 2, 3), (4, 5, 6), (7, 8, 9)를 포함하는 것으로 가정합니다. 변환 후 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열은 1, 2, 3, 4, 5, 6, 7, 8, 9를 포함합니다.  
  
 현재 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열을 VBArray 배열로 변환할 방법은 없습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 세 부분으로 구성됩니다. 첫 번째 부분은 Visual Basic 안전 배열을 만드는 VBScript 코드입니다. 두 번째 부분은 Visual Basic 안전 배열을 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 배열로 변환하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드입니다. 로 이동 하는 두 부분 모두는 \<H e a d > HTML 페이지의 섹션입니다. 세 번째 부분은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에 사용 되는 코드는 \<본문 > 섹션을 두 부분을 실행 합니다.  
  
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
         a(j, i) = k  
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
function VBArrayTest(vbarray)  
{  
   var a = new VBArray(vbarray);  
   var b = a.toArray();  
   var i;  
   for (i = 0; i < 9; i++)   
   {  
      document.writeln(b[i]);  
   }  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
<!--  
   VBArrayTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [VBArray Object](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [dimensions 메서드 (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [getItem 메서드 (VBArray)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [lbound 메서드 (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [ubound 메서드(VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)