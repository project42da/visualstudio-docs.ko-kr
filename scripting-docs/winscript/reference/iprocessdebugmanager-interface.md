---
title: "IProcessDebugManager 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IProcessDebugManager interface
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26c97fda6fc8657164e22d51eb041017a6239d98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iprocessdebugmanager-interface"></a>IProcessDebugManager 인터페이스
디버그 프로세스 관리자에 게 기본 인터페이스입니다. 이 인터페이스 작성 수, 추가 또는 프로세스에서 가상 응용 프로그램을 제거 합니다. 스택 프레임 및 응용 프로그램 스레드를 열거할 수 있습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IProcessDebugManager` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|이 응용 프로그램에 대 한 새 디버그 응용 프로그램 개체를 만듭니다.|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|현재 프로세스에 대 한 기본 응용 프로그램 개체를 반환합니다.|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|실행 중인 응용 프로그램의 컴퓨터 디버그 관리자 목록에 응용 프로그램을 추가 합니다.|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|실행 되는 응용 프로그램을 제거 응용 프로그램 목록입니다.|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|이 응용 프로그램에 대 한 새 디버그 문서 도우미를 만듭니다.|