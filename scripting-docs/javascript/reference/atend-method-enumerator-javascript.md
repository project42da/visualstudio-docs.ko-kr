---
title: "atEnd 메서드 (Enumerator) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atEnd
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: atEnd method
ms.assetid: 326808fb-9a0f-428e-aff1-b11b237913f1
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b5097d00c11ffafc314264f134aedda3981c8e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="atend-method-enumerator-javascript"></a>atEnd 메서드(Enumerator)(JavaScript)
열거자가 컬렉션의 끝에 있는지를 나타내는 부울 값을 반환합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
myEnum.atEnd()  
```  
  
## <a name="remarks"></a>설명  
 필요한 *myEnum* 참조는 모든 `Enumerator` 개체입니다.  
  
 현재 항목이 컬렉션의 마지막 항목이거나 컬렉션이 비어 있거나 현재 항목 정의되지 않은 경우 `atEnd` 메서드는 **true** 를 반환합니다. 그렇지 않으면 **false**를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 드라이브 목록 끝에 도달했는지 확인하기 위해 `atEnd` 메서드가 사용됩니다.  
  
```JavaScript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다. [버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [Enumerator Object](../../javascript/reference/enumerator-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [item 메서드 (Enumerator)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveFirst 메서드 (Enumerator)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext 메서드 (Enumerator)](../../javascript/reference/movenext-method-enumerator-javascript.md)   
 [Enumerator 개체](../../javascript/reference/enumerator-object-javascript.md)