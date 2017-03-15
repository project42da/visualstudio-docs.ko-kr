---
title: "프로그램에서 단계별로 실행하는 경우 어떻게 포커스를 유지할 수 있습니까? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.stepping"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "디버깅[C++], 단계별 실행"
  - "포커스, 유지"
  - "단계별 실행, 포커스"
  - "windows, 활성화 문제 해결"
ms.assetid: 11a30580-3a1a-4be8-a241-0abdc758302e
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로그램에서 단계별로 실행하는 경우 어떻게 포커스를 유지할 수 있습니까?
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

## 설명  
 프로그램에 창 활성화에 대한 문제가 생겼습니다.  프로그램에서 단계별로 디버거를 실행하면 프로그램이 계속해서 포커스를 잃어 버리기 때문에 문제 재현 기능이 방해를 받습니다.  어떻게 해결할 수 있습니까?  
  
## 해결책  
 다른 컴퓨터가 있을 경우 원격 디버깅을 사용합니다.  호스트에서 디버거를 실행하는 동안 원격 컴퓨터에서 프로그램을 작동시킬 수 있습니다.  자세한 내용은 [How to: Select a Remote Computer](http://msdn.microsoft.com/ko-kr/4332ba8e-2f0b-4f62-b96a-e762b9f3c3ba)을 참조하십시오.  
  
## 참고 항목  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)   
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)