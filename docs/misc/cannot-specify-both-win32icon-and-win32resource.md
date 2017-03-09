---
title: "/win32icon과 /win32resource를 둘 다 지정할 수는 없습니다. | Microsoft Docs"
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
  - "vbc2023"
  - "bc2023"
helpviewer_keywords: 
  - "BC2023"
ms.assetid: 60914807-1fde-4fef-9c6f-6f4a62527eed
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32icon과 /win32resource를 둘 다 지정할 수는 없습니다.
`/win32resource`와 `/win32icon` 옵션은 아이콘 정보를 출력 파일에 삽입하기 때문에 함께 사용할 수 없습니다.  
  
 **오류 ID:** BC2023  
  
### 이 오류를 해결하려면  
  
-   .ico 파일을 출력 파일에 삽입하려면 `/win32icon` 옵션만 사용합니다. 이 .ico 파일은 Windows 탐색기에서 출력 파일을 나타냅니다.  
  
     — 또는 —  
  
-   Win32 리소스 파일을 출력 파일에 삽입하려면 `/win32resource` 옵션만 사용합니다. Win32 리소스는 Windows 탐색기에서 응용 프로그램을 식별하는 데 도움이 되는 버전 정보나 비트맵\(아이콘\) 정보를 포함할 수 있습니다.  
  
## 참고 항목  
 [\/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon)   
 [\/win32resource](/dotnet/visual-basic/reference/command-line-compiler/win32resource)