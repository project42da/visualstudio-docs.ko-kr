---
title: "moveNext 메서드 (Enumerator) (JavaScript) | Microsoft Docs"
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
- moveNext
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- MoveNext method
ms.assetid: 59aa339b-f375-450a-8276-37896a55a824
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab9b07a9a9c4640407cff0eaf21a6e8cd65dac11
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="movenext-method-enumerator-javascript"></a>moveNext 메서드(Enumerator)(JavaScript)
현재 항목을 컬렉션의 다음 항목으로 이동합니다.  
  
> [!WARNING]
>  이 개체는 Internet Explorer에서만 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
enumObj.moveNext( )   
```  
  
## <a name="remarks"></a>설명  
 필요한 *enumObj* 참조는 모든 `Enumerator` 개체입니다.  
  
 열거자가 컬렉션의 끝에 있거나 컬렉션이 비어 있는 경우 현재 항목이 정의되지 않음으로 설정됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **컬렉션에서 다음 드라이브로 이동하는 데** moveNext `Drives` 메서드가 사용됩니다.  
  
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
 [item 메서드 (Enumerator)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveFirst 메서드(Enumerator)](../../javascript/reference/movefirst-method-enumerator-javascript.md)