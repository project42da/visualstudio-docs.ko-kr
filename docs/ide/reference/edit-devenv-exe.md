---
title: "/Edit (devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/Edit Devenv 스위치"
  - "Devenv, /edit 스위치"
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Edit (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에서 지정된 파일을 엽니다.  
  
## 구문  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## 인수  
 `file1`  
 선택적 요소.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에서 열려는 파일입니다.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 인스턴스가 없으면 간단한 창 레이아웃을 사용하여 새 인스턴스가 만들어지고 `file1`이 새 인스턴스에 열립니다.  
  
 `file2`  
 선택적 요소.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에서 열려는 하나 이상의 추가 파일입니다.  
  
## 설명  
 파일을 지정하지 않았지만 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 있으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에 포커스가 놓입니다.  파일을 지정하지 않았고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스도 없으면 간단한 창 레이아웃을 사용하여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 새 인스턴스가 만들어집니다.  
  
 [옵션 대화 상자](../../ide/reference/options-dialog-box-visual-studio.md)가 열려 있는 경우와 같이 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스가 모달 상태인 경우에는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 모달 상태가 종료될 때 기존 인스턴스에 파일이 열립니다.  
  
## 예제  
 이 예제에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 기존 인스턴스에 `MyFile.cs` 파일을 열거나 기존 인스턴스가 없는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]의 새 인스턴스에 파일을 엽니다.  
  
```  
devenv /edit MyFile.cs  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)