---
title: "No files were found to look in. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_FRLookInEmpty"
  - "vs.message.0x800A00DE"
ms.assetid: d560aef3-7a55-4fbb-a541-1a43fc13c18b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# No files were found to look in.
이 오류는 찾는 위치 목록에 파일 이름 또는 디렉터리를 지정했지만 해당 파일 이름 또는 디렉터리가 없거나 이를 찾을 수 없는 경우 발생합니다.  또한 파일 형식 목록에 지정된 파일 확장명을 포함하지 않은 디렉터리를 지정하거나 지정된 디렉터리에 파일이 없는 경우에도 이 오류가 나타날 수 있습니다.  `Hidden` 또는 `System` 특성이 설정된 디렉터리에서 검색할 때도 오류가 나타날 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  경로나 파일 이름을 입력하는 대신 **사용자 지정 구성 요소 집합** 대화 상자를 사용하여 검색할 디렉터리 또는 파일 이름을 찾아봅니다.  **찾는 위치** 목록 옆에 있는 줄임표 단추를 선택하여 **사용자 지정 구성 요소 집합** 대화 상자에 액세스할 수 있습니다.  
  
2.  **파일 형식** 목록에 지정된 파일 확장명을 \*.\*로 변경하여 지정된 디렉터리에 있는 모든 파일을 검색합니다.  
  
### 이 오류를 무시하려면  
  
1.  Ctrl 키를 누른 채로 ScrLk 키를 누릅니다.  
  
     그러면 대화 상자가 취소됩니다.  
  
## 참고 항목  
 [텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)   
 [파일에서 찾기](../ide/find-in-files.md)   
 [Choose Search Folders](http://msdn.microsoft.com/ko-kr/85af6458-dcde-4a84-9ea4-f5cc6550dc80)