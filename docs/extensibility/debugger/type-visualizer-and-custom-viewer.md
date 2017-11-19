---
title: "시각화 도우미와 사용자 지정 뷰어를 입력 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80798887beee6116b3a93b5d8ec86b14269b5475
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="type-visualizer-and-custom-viewer"></a>사용자 지정 뷰어와 형식 시각화 도우미
형식 시각화 도우미는 매우 구체적인 형식으로 데이터를 표시 하는 구성 요소입니다. 이 형식은 전적으로 시각화 도우미의 구현자에 따라, 최종 사용자 또는 타사 공급 업체가 제공한 시각화 도우미의 수입니다.  
  
 사용자 지정 뷰어는 데이터의 일부는 매우 구체적인 형식으로 표시 하는 사용자 지정 식 계산기의 일부입니다. 이 형식은 전적으로 식 계산기 (EE)의 구현 자가 형식으로는 사용자 지정 뷰어를 구현 합니다.  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>식 계산기에 형식 시각화 도우미에 대 한 지원  
 일련의 시각화 도우미에 액세스할 수 있는 인터페이스를 지원 하 여 형식 시각화 도우미를 지원할 수는 EE:와 같은 인터페이스 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) 및 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)합니다. 단, EE은 자체 형식 시각화 도우미를 구현 하는 일을 담당 하지 않습니다: EE 단순히 외부 시각화 도우미에 액세스할 수 있도록 해당 형식 정보입니다. 이러한 시각화 도우미는 EE 함께 제공 수도 있으며도 최종 사용자가 또는 다른 타사 공급 업체에서 제공 하는 Visual Studio에서 적절 한 위치에 설치 됩니다.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>사용자 지정 뷰어에 식 계산기에 대 한 지원  
 EE 자체는 EE 데이터 형식 보기에 대 한 코드를 제공 하는 사용자 지정 뷰어도 지원할 수 있습니다. 사용자 지정 뷰어를 구현 하는 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) 인터페이스의 모든 형식에 데이터를 표시 하는 모든 직무를 처리 하는 원하는; 뷰어에 표시에 대 한 모든 권한을 있으며 데이터를 수정할 수 허용할 수도 있습니다. 제품 배송 시 EE는 EE에서 제공 된 모든 사용자 지정 뷰어가 제공 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)   
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)