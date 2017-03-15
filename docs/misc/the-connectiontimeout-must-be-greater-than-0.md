---
title: "ConnectionTimeout은 0보다 커야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrNetwork_BadConnectionTimeout"
ms.assetid: 15ac09a7-47f0-44f3-9e84-5bd10bd07450
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ConnectionTimeout은 0보다 커야 합니다.
[My.Computer.Network Object](/dotnet/visual-basic/language-reference/objects/my-computer-network-object)를 사용하여 파일을 업로드 및 다운로드할 때 `0`보다 큰 `connectionTimeout`을 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `0`보다 큰 `connectionTimeout`을 제공합니다.  
  
## 참고 항목  
 [My.Computer.Network.UploadFile 메서드](http://msdn.microsoft.com/ko-kr/5505ea3e-3dbd-460b-9f8f-62c84c0a4de6)   
 [My.Computer.Network.DownloadFile 메서드](http://msdn.microsoft.com/ko-kr/aeb7ed8f-1ac9-4242-ae57-9f35914eb329)   
 [How to: Upload a File](../Topic/How%20to:%20Upload%20a%20File%20in%20Visual%20Basic.md)   
 [How to: Download a File](../Topic/How%20to:%20Download%20a%20File%20in%20Visual%20Basic.md)   
 [Visual Basic을 사용한 .NET Framework의 네트워크 작업](http://msdn.microsoft.com/ko-kr/c5379021-44ef-4d6a-acf5-e951fdcab6b2)