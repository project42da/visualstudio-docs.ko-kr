---
title: "인코딩은 Nothing으로 설정할 수 없음 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인코딩은 Nothing으로 설정할 수 없음
`encoding` 매개 변수가 `Nothing`으로 설정되었지만 유효한 값이 필요하기 때문에 파일에서 읽거나 쓰려는 시도가 실패했습니다.  
  
 <xref:System.Text.Encoding>은 파일에 쓸 때 사용할 인코딩을 결정하기 위해 사용됩니다. 기본값은 UTF\-8입니다.  
  
### 이 오류를 해결하려면  
  
-   `encoding` 매개 변수에 대한 유효한 값을 제공합니다.  
  
## 참고 항목  
 [File Encodings](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/file-encodings)   
 [Reading from Files](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/reading-from-files)   
 [Writing to Files](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/writing-to-files)   
 [My.Computer.FileSystem.ReadAllText 메서드](http://msdn.microsoft.com/ko-kr/3a7ac8be-fb1d-4087-bc65-167d6754d57f)   
 [My.Computer.FileSystem.WriteAllText 메서드](http://msdn.microsoft.com/ko-kr/f507460c-87d9-4504-b74f-3ff825c7d5c4)