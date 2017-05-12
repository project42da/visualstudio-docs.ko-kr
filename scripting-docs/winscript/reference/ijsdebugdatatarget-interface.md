---
title: "IJsDebugDataTarget 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a9b784d6-958f-4d55-b3f6-c2d6b260a16b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget 인터페이스
대상 디버거 프로세스의 상태에 액세스하고 변경하는 기능을 제공하기 위해 디버거에 의해 구현되었습니다.  
  
## 구문  
  
```  
IJsDebugDataTarget : public IUnknown;  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IJsDebugDataTarget::AllocateVirtualMemory 메서드](../../winscript/reference/ijsdebugdatatarget-allocatevirtualmemory-method.md)|대상 프로세스의 가상 주소 공간 내의 메모리 영역 예약 및\/또는 커밋|  
|[IJsDebugDataTarget::CreateStackFrameEnumerator 메서드](../../winscript/reference/ijsdebugdatatarget-createstackframeenumerator-method.md)|스택 프레임에 대한 열거자를 만듭니다.|  
|[IJsDebugDataTarget::FreeVirtualMemory 메서드](../../winscript/reference/ijsdebugdatatarget-freevirtualmemory-method.md)|대상 프로세스의 가상 주소 공간 내의 메모리 영역 해제 및\/또는 커밋 해제|  
|[IJsDebugDataTarget::GetThreadContext 메서드](../../winscript/reference/ijsdebugdatatarget-getthreadcontext-method.md)|스레드가 제공하는 컨텍스트를 검색합니다.|  
|[IJsDebugDataTarget::GetTlsValue 메서드](../../winscript/reference/ijsdebugdatatarget-gettlsvalue-method.md)|디버깅 중인 스레드의 경우 지정된 TLS 인덱스에 대해 TLS\(스레드 로컬 저장소\)에서 값을 검색합니다.|  
|[IJsDebugDataTarget::ReadBSTR 메서드](../../winscript/reference/ijsdebugdatatarget-readbstr-method.md)|디버그 대상에서 읽히는 BSTR을 읽습니다.|  
|[IJsDebugDataTarget::ReadMemory 메서드](../../winscript/reference/ijsdebugdatatarget-readmemory-method.md)|대상 프로세스의 메모리를 읽습니다.|  
|[IJsDebugDataTarget::ReadNullTerminatedString 메서드](../../winscript/reference/ijsdebugdatatarget-readnullterminatedstring-method.md)|대상에서 지정한 문자 수를 읽습니다.|  
|[IJsDebugDataTarget::WriteMemory 메서드](../../winscript/reference/ijsdebugdatatarget-writememory-method.md)|대상 프로세스의 메모리를 읽습니다.|  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)