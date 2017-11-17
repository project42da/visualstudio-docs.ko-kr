---
title: "Enumerator 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Enumerator
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Enumerator object
ms.assetid: 63f03c21-d58c-47db-a728-4d8d88b0a422
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50b1ebfb6e24ed734f008b3c05f10a1687c4aff5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="enumerator-object-javascript"></a>Enumerator 개체(JavaScript)
컬렉션에서 항목을 열거할 수 있도록 설정합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원되고, [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
enumObj = new Enumerator([collection])   
```  
  
## <a name="parameters"></a>매개 변수  
 `enumObj`  
 필수 요소. `Enumerator` 개체가 할당되는 변수 이름입니다.  
  
 `collection`  
 선택적 요소. 모든 컬렉션 개체입니다.  
  
## <a name="remarks"></a>설명  
 컬렉션의 멤버는 직접 액세스할 수 없다는 점에서 컬렉션과 배열은 다릅니다. 인덱스를 사용하는 대신 배열를 사용하면 현재 항목 포인터를 컬렉션의 첫 번째 또는 다음 요소로만 이동할 수 있습니다.  
  
 `Enumerator` 개체는 컬렉션의 모든 멤버에 액세스하는 방법을 제공하고 VBScript의 `For...Each` 문과 유사하게 동작합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Enumerator` 개체의 사용법을 보여 줍니다.  
  
```JavaScript  
var bytesPerGB = 1024 * 1024 * 1024;  
  
var fso = new ActiveXObject("Scripting.FileSystemObject");  
  
document.write(fso.Drives);  
var e = new Enumerator(fso.Drives);  
  
var driveString = "";  
  
e.moveFirst();  
while (e.atEnd() == false)  
{  
    var drv = e.item();  
  
    driveString += drv.Path + " - ";  
  
    if (drv.IsReady){  
        var freeGB = drv.FreeSpace / bytesPerGB;  
        var totalGB = drv.TotalSize / bytesPerGB;  
  
        driveString += freeGB.toFixed(3) + " GB free of ";  
        driveString += totalGB.toFixed(3) + " GB";  
    }  
    else{  
        driveString += "Not Ready";  
    }  
  
    driveString += "<br />";;  
  
    e.moveNext();  
}  
document.write(driveString);  
  
// Output: <drive information  
  
```  
  
## <a name="properties"></a>속성  
 `Enumerator` 개체에는 속성이 없습니다.  
  
## <a name="methods"></a>메서드  
 [atEnd 메서드](../../javascript/reference/atend-method-enumerator-javascript.md) &#124; [item 메서드](../../javascript/reference/item-method-enumerator-javascript.md) &#124; [moveFirst 메서드](../../javascript/reference/movefirst-method-enumerator-javascript.md) &#124; [moveNext 메서드](../../javascript/reference/movenext-method-enumerator-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)