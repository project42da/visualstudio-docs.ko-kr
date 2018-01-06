---
title: "포트 공급자 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: aa70e2a6019a97c248e6d4b411dacc222be59a1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-port-supplier"></a>포트 공급자 구현
포트 공급자 세션 디버그 관리자 (SDM)에 요청에서 포트를 제공합니다. 포트 공급자 때나 새 장치를 지원 해야 합니다. DCOM이 아닌 컴퓨터에 디버깅할 때 구현 해야 합니다. 예를 들어 휴대 전화에 디버깅을 제공 하려면 (아마도 IR 또는 연결을 통해는 셀) 휴대 전화에 연결 하 고 휴대폰에서 실행 되는 프로그램 및 프로세스를 열거 하는 포트를 제공 하는 포트 공급자를 구현할 수 있습니다.  
  
 Windows 기반 컴퓨터 (원격 디버깅 포함)에서 디버깅 프로그램에 대 한 Visual Studio 이므로 경우에서 고유한 포트 공급자를 구현할 필요가 없습니다 네이티브 및 공용 언어 런타임 (CLR) 프로세스에 대 한 포트 공급자를 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [포트 공급자 구현 및 등록](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 SDM 포트 공급자 및 해당 포트와 상호 작용 하는 방법에 대해 설명 합니다.  
  
 [필요한 포트 공급자 인터페이스](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 가져올 포트 공급자를 구현 해야 하는 인터페이스에 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)