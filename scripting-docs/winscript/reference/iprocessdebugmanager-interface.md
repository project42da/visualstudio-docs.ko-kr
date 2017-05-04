---
title: "IProcessDebugManager 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IProcessDebugManager 인터페이스"
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IProcessDebugManager 인터페이스
기본 프로세스 디버그 관리자 인터페이스입니다.  이 인터페이스 작성 하 고, 추가 또는 프로세스에서 가상 응용 프로그램을 제거 합니다.  응용 프로그램 스레드 및 스택 프레임을 열거할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IProcessDebugManager` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|이 응용 프로그램에 대 한 새 디버그 응용 프로그램 개체를 만듭니다.|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|현재 프로세스에 대 한 기본 응용 프로그램 개체를 반환합니다.|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|실행 중인 응용 프로그램의 응용 프로그램 컴퓨터 디버그 관리자 목록에 추가 합니다.|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|응용 프로그램 실행에서 제거 응용 프로그램 목록입니다.|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|새 디버그 문서 도우미 응용 프로그램을 만듭니다.|