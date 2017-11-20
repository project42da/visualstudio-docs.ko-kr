---
title: "WinRTError 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- WinRTError object [JavaScript]
- JavaScript, WinRTError object
ms.assetid: d75ab8e5-e729-4d86-90fd-ea228c30dd66
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11b339b4fc3c4bd4f34416ffd98b8f9c3f288f98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="winrterror-object-javascript"></a>WinRTError 개체(JavaScript)
Windows 런타임 호출 시 오류를 나타내는 HRESULT가 반환되면 JavaScript는 해당 HRESULT를 특수한 Windows 런타임 오류로 변환합니다. 이 오류는 Windows 런타임을 사용할 수 있을 때 전역 JavaScript 네임스페이스의 일부분으로 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서만 사용 가능합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
errorObj = new WinRTError();  
  
```  
  
## <a name="remarks"></a>설명  
 WinRTError 오류 유형은 Windows 런타임 API에서 발생하는 오류에만 사용됩니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 WinRTError가 throw 및 catch되는 방식을 보여 줍니다.  
  
```JavaScript  
try {  
            Windows.Storage.ApplicationData.localFolder.createFileAsync("sample.txt");  
        } catch (err) {  
            var n = err;  
        }  
  
```  
  
## <a name="methods"></a>메서드  
 WinRTError 개체에는 메서드가 없습니다.  
  
## <a name="properties"></a>속성  
 WinRTError 개체에는 동일한 속성으로는 [Error 개체](../../javascript/reference/error-object-javascript.md) 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 WinRTError 개체는 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서만 지원되며 Internet Explorer에서는 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)