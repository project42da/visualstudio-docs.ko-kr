---
title: "item 메서드 (Enumerator) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: item
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Item method
ms.assetid: a88e93f2-42df-4578-a4f9-0760bd074185
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94275b2c82f199c96ef2d6c7d667fd27fba2702d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="item-method-enumerator-javascript"></a>item 메서드(Enumerator)(JavaScript)
컬렉션의 현재 항목을 반환합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
enumObj.item()   
```  
  
## <a name="remarks"></a>설명  
 필요한 *enumObj* 참조는 모든 `Enumerator` 개체입니다.  
  
 **item** 메서드는 현재 항목을 반환합니다. 컬렉션은 비어 있거나 현재 항목이 정의되지 않은 경우 **undefined**를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 **컬렉션의 멤버를 반환하기 위해** item `Drives` 메서드가 사용됩니다.  
  
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
 [atEnd 메서드 (Enumerator)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [moveFirst 메서드 (Enumerator)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext 메서드(Enumerator)](../../javascript/reference/movenext-method-enumerator-javascript.md)