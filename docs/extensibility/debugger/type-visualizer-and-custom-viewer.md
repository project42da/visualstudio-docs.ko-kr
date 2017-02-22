---
title: "시각화 도우미 형식 및 사용자 지정 뷰어 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 사용자 지정 뷰어"
  - "디버깅 [디버깅 SDK] 형식 시각화 도우미"
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 시각화 도우미 형식 및 사용자 지정 뷰어
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

형식을 시각화 도우미 데이터를 특정 형식으로 표시 하는 구성 요소입니다.  이 형식을 시각화 도우미의 구현자를 전적으로, 최종 사용자 또는 타사 공급 업체의 시각화 도우미 될.  
  
 사용자 지정 뷰어에서 데이터를 특정 형식으로 표시 하는 사용자 지정 식 계산기의 일부입니다.  이 형식은 전적으로 구현 자가 사용자 지정 뷰어 형식 식 계산기 \(EE\)의 구현 자가 설치 하는 것입니다.  
  
## 식 계산기에서 형식 시각화 도우미에 대 한 지원  
 시각화 도우미에 액세스할 수 있는 인터페이스 집합을 지원 하 여 형식을 시각화 도우미는 EE를 지원할 수 있습니다: 같은 인터페이스 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) 및 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md).  그러나 EE 구현 형식을 시각화 하는 다릅니다: EE 단지 외부 시각화 도우미의 형식 정보에 액세스할 수 있습니다.  이러한 시각화 도우미 EE와 함께 제공 된 고 적절 한 위치에 다른 제 3의 공급 업체 또는 최종 사용자에 게 제공 Visual Studio 설치 되어 있습니다.  
  
## 식 계산기에 사용자 지정 뷰어 지원  
 수도 EE에서 EE 자체 데이터 형식을 보고 하는 코드를 제공 하는 사용자 지정 뷰어를 지원할 수 있습니다.  사용자 지정 표시기 구현에서 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) 의 서식에 필요한 경우; 데이터를 보여 주는 모든 업무를 처리 하는 인터페이스 전체 디스플레이 제어할 수 있습니다 뷰어와 수정 해야 하는 데이터를 사용할 수도 있습니다.  제품 배송 시 EE에서 제공 된 사용자 지정 뷰어는 EE에 제공 됩니다.  
  
## 참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)