---
title: "프로젝트 형식이 이 설치에서 지원되지 않음 | Microsoft Docs"
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
  - "vs.projectflavornotavailable"
ms.assetid: 50e92aff-3ce9-4600-94af-4a16e9dffc90
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 프로젝트 형식이 이 설치에서 지원되지 않음
이 오류는 Visual Studio 설치 되어 있지 않은 소프트웨어 개발 키트 \(SDK\)를 필요로 하는 프로젝트 형식을 열려고 할 때 발생 합니다.  예를 들어, 이 오류는 Visual Studio SDK 설치 되어 있지 않은 컴퓨터에서 Visual Studio를 여는 경우에 발생하고 그렇다면 VSIX 프로젝트와 같은 해당 SDK에 대한 프로젝트 파일을 열려고 시도 하십시오. \(Visual Studio SDK에 대한 자세한 내용은 [Visual Studio 확장](http://go.microsoft.com/fwlink/?LinkID=64968)을 참조하십시오.\)  
  
## 해결 방법  
 열려고 하는 프로젝트의 형식에 대한 정확한 SDK가 설치되었는지 확인 해야 합니다.  
  
#### 이미 SDK가 설치 되어 있는지 여부를 확인 하려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자에서, **설치된** 를 확장하고, **템플릿** 을 확장한 다음, **다른 프로젝트 타입** 노드를 선택합니다.  
  
3.  열려고 하는 프로젝트를 사용할 수 있는지 여부를 확인 하려면 사용할 수 있는 프로젝트 형식을 검토 합니다.  
  
 열려고 하는 프로젝트의 종류를 찾을 수 없으면, 관련된 SDK가 설치가 되어 있지 않는 것입니다.  프로젝트 형식을 열 관련된 SDK를 설치하고 배치시켜야 합니다.  
  
## 참고 항목  
 [Visual Studio 2015의 새로운 기능](../ide/what-s-new-in-visual-studio-2015.md)   
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)