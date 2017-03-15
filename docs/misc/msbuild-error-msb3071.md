---
title: "MSBuild 오류 MSB3071 | Microsoft Docs"
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
  - "MSBuild.Exec.AllDriveLettersMappedError"
helpviewer_keywords: 
  - "MSB3071"
ms.assetid: 8afbc6ec-e399-4f06-a30b-f33c87642ef7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3071
**A:에서 Z:까지 모든 드라이브 문자가 현재 사용 중입니다.  작업 디렉터리 "'\<path\>'"이\(가\) UNC 경로이므로 "Exec" 작업을 수행하려면 UNC 경로를 매핑하는 데 사용할 수 있는 드라이브 문자가 필요합니다.  하나 이상의 공유 리소스에서 연결을 끊어 사용 가능한 드라이브 문자를 만들거나 로컬 작업 디렉터리를 지정한 다음 이 명령을 다시 실행하십시오.**  
  
 A:에서 Z:까지 모든 드라이브 문자가 현재 사용 중입니다.  지정된 작업 디렉터리가 UNC 경로이므로 `Exec` 작업을 수행하려면 UNC 경로를 매핑하는 데 사용할 수 있는 드라이브 문자가 필요합니다.  
  
### 이 오류를 해결하려면  
  
-   하나 이상의 공유 리소스 연결을 끊어 사용 가능한 드라이브 문자를 확보합니다.  
  
-   로컬 작업 디렉터리를 지정한 다음 이 명령을 다시 시도합니다.  
  
## 참고 항목  
 [Exec Task](../msbuild/exec-task.md)