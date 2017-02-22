---
title: "IDebugIDECallback | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugIDECallback 인터페이스"
ms.assetid: 8d31adc0-1c44-4658-8d4f-f4b73e35f4a6
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugIDECallback
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 디버거의 출력 창에 메시지를 표시 하는 식 계산기를 \(EE\) 수 있습니다.  
  
## 구문  
  
```  
IDebugIDECallback : IUnknown  
```  
  
## 구현자를 위한 정보  
 이 콜백은 관리 되는 디버그 엔진에 의해 구현 됩니다.  
  
## 호출자에 대 한 참고 사항  
 디버거의 출력 창에 출력을 보낼 식 계산기에서 사용할 수 있습니다.  
  
## 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[메시지 표시](../../../extensibility/debugger/reference/idebugidecallback-displaymessage.md)|디버거의 출력 창에 지정 된 메시지 문자열을 보냅니다.|  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll