---
title: "VBArray 개체 (JavaScript) | Microsoft Docs"
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
- VBArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- VBArray object constant
ms.assetid: f0b767f1-ea8a-4726-962b-2708d4742518
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b86e261a0cef445f1e0e0ecd651d5eb283cffce1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="vbarray-object-javascript"></a>VBArray 개체(JavaScript)
Visual Basic 안전 배열 액세스 권한을 제공합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원되고, [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
varName = new VBArray(safeArray)   
```  
  
## <a name="parameters"></a>매개 변수  
 `varName`  
 필수 요소. VBArray가 할당되는 변수 이름입니다.  
  
 *safeArray*  
 필수 요소. VBArray 값입니다.  
  
## <a name="remarks"></a>설명  
 VBArrays는 읽기 전용이므로 직접 만들 수 없습니다. *safeArray* 인수를 VBArray 생성자로 전달하려면 먼저 VBArray 값을 가져와야 합니다. 이 작업은 기존 ActiveX 또는 다른 개체에서 값을 검색하는 방식으로만 수행할 수 있습니다.  
  
 VBArray에는 여러 차원이 있을 수 있으며, 각 차원의 인덱스는 다를 수 있습니다. **dimensions** 메서드는 배열의 차원 수를 검색하고, `lbound` 및 `ubound` 메서드는 각 차원에서 사용하는 인덱스의 범위를 검색합니다.  
  
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
      document.writeln("<br />")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vbarray){  
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
  
## <a name="properties"></a>속성  
 `VBArray` 개체에는 속성이 없습니다.  
  
## <a name="methods"></a>메서드  
 [dimensions 메서드](../../javascript/reference/dimensions-method-vbarray-javascript.md) &#124; [getItem 메서드](../../javascript/reference/getitem-method-vbarray-javascript.md) &#124; [lbound 메서드](../../javascript/reference/lbound-method-vbarray-javascript.md) &#124; [toArray 메서드](../../javascript/reference/toarray-method-vbarray-javascript.md) &#124; [ubound 메서드](../../javascript/reference/ubound-method-vbarray-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Array 개체](../../javascript/reference/array-object-javascript.md)