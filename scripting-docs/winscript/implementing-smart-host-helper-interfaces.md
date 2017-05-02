---
title: "스마트 호스트 도우미 인터페이스 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "스마트 호스트 도우미 인터페이스, 구현"
ms.assetid: b9c44246-4d4d-469e-91be-00c8f5796fa5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 스마트 호스트 도우미 인터페이스 구현
[IDebugDocumentHelper 인터페이스](../winscript/reference/idebugdocumenthelper-interface.md) 인터페이스 간소화 활성 디버깅에 대 한 스마트 호스트를 작성 하는 작업 스마트 호스팅하는 데 필요한 많은 인터페이스에 대 한 구현을 제공 하기 때문에.  
  
 스마트 호스트를 사용 하려면 `IDebugDocumentHelper`, 호스트 응용 프로그램은 세 가지 작업을 수행 해야 합니다.  
  
1.  `CoCreate`프로세스 디버그 관리자 및 사용 된 [IProcessDebugManager 인터페이스](../winscript/reference/iprocessdebugmanager-interface.md) 인터페이스 응용 프로그램을 디버깅할 수 있는 응용 프로그램 목록에 추가 합니다.  
  
2.  만들 각 스크립트에 대 한 디버그 문서 도우미 개체를 사용 하는 [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md) 메서드.  문서 이름, 상위 문서, 텍스트 및 스크립트 블록에 정의 되어 있는지 확인 합니다.  
  
3.  구현에서 [IActiveScriptSiteDebug 인터페이스](../winscript/reference/iactivescriptsitedebug-interface.md) 인터페이스를 구현 하는 개체에는 [IActiveScriptSite](../winscript/reference/iactivescriptsite.md) \(Active 스크립팅의 경우 필요\) 인터페이스.  에 특수 메서드는 `IActiveScriptSiteDebug` 인터페이스는 단순히 도우미에 위임 합니다.  
  
 호스트를 선택적으로 구현할 수 있는 [IDebugDocumentHost 인터페이스](../winscript/reference/idebugdocumenthost-interface.md) 인터페이스 컨트롤 구문 색상, 문서 컨텍스트 작성 및 기타 확장된 기능을 추가로 필요한 경우.  
  
 스마트 호스트 도우미에 큰 제한은 문서 내용이 변경 또는 축소 \(문서를 확장할 수 있지만\)가 추가 된 후만 처리할 수 있습니다.  그러나 여러 스마트 호스트에 대 한 제공 기능 정확 하 게 필요 합니다.  
  
 다음 섹션에서는 각 단계에 자세히 설명합니다.  
  
## 응용 프로그램 개체를 만듭니다.  
 스마트 호스트 도우미 사용 하기 전에 만들 필요는 있는 [IDebugApplication 인터페이스](../winscript/reference/idebugapplication-interface.md) 디버거에서 응용 프로그램을 나타내는 개체입니다.  
  
#### 응용 프로그램 개체를 만들려면  
  
1.  인스턴스의 프로세스 디버그 관리자를 사용 하 여 만드는 `CoCreateInstance`.  
  
2.  [IProcessDebugManager::CreateApplication](../winscript/reference/iprocessdebugmanager-createapplication.md)를 호출합니다.  
  
3.  사용 하 여 응용 프로그램의 이름을 설정 [IDebugApplication::SetName](../winscript/reference/idebugapplication-setname.md).  
  
4.  사용 하 여 응용 프로그램 개체를 디버깅할 수 있는 응용 프로그램 목록에 추가 [IProcessDebugManager::AddApplication](../winscript/reference/iprocessdebugmanager-addapplication.md).  
  
     아래 코드는 프로세스에 설명 하지만 오류 검사 또는 기타 강력한 프로그래밍 기술을 포함 하지 않습니다.  
  
    ```  
    CoCreateInstance(CLSID_ProcessDebugManager, NULL,  
          CLSCTX_INPROC_SERVER | CLSCTX_INPROC_HANDLER  
          | CLSCTX_LOCAL_SERVER,  
    IID_IProcessDebugManager, (void **)&g_ppdm);  
    g_ppdm->CreateApplication(&g_pda);  
    g_pda->SetName(L"My cool application");  
    g_ppdm->AddApplication(g_pda, &g_dwAppCookie);  
    ```  
  
## Idebugdocumenthelper를 사용합니다.  
  
#### 도우미 \(최소 시퀀스의 단계\)를 사용 합니다.  
  
1.  각 호스트 문서를 사용 하는 도우미 만들기 [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md).  
  
2.  호출 [IDebugDocumentHelper::Init](../winscript/reference/idebugdocumenthelper-init.md) 이름, 문서 속성 등에서 도우미를 제공 합니다.  
  
3.  호출 [IDebugDocumentHelper::Attach](../winscript/reference/idebugdocumenthelper-attach.md) 부모 도우미 문서 \(또는 루트 문서가 있는 경우 NULL\)를 트리에서 문서의 위치를 정의 하 고 디버거를 보이게 합니다.  
  
4.  호출 [IDebugDocumentHelper::AddDBCSText](../winscript/reference/idebugdocumenthelper-adddbcstext.md) 또는 [IDebugDocumentHelper::AddUnicodeText](../winscript/reference/idebugdocumenthelper-addunicodetext.md) 문서의 텍스트를 정의 합니다.  \(브라우저의 경우와 같이 문서의 점진적으로 다운로드 하는 경우 이러한 여러 번 호출할 수 있습니다.\)  
  
5.  호출 [IDebugDocumentHelper::DefineScriptBlock](../winscript/reference/idebugdocumenthelper-definescriptblock.md) 는 각 스크립트 블록과 연결 된 스크립트 엔진에 대 한 범위를 정의 합니다.  
  
## Iactivescriptsitedebug를 구현합니다.  
 구현 하기 [IActiveScriptSiteDebug::GetDocumentContextFromPosition](../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md), 특정된 사이트에 해당 하는 도우미를 가져오고 다음 컨텍스트에 대해 지정 된 소스를 같이 오프셋 시작 문서를 가져옵니다.  
  
```  
pddh->GetScriptBlockInfo(dwSourceContext, NULL, &ulStartPos, NULL);  
```  
  
 그런 다음 도우미 지정 된 문자 오프셋에 대 한 새 문서 컨텍스트를 만드는 데 사용 합니다.  
  
```  
pddh->CreateDebugDocumentContext(ulStartPos + uCharacterOffset, cChars, &pddcNew);  
```  
  
 구현에 [IActiveScriptSiteDebug::GetRootApplicationNode](../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)를 호출 하면 `IDebugApplication::GetRootNode` \(상속 [IRemoteDebugApplication::GetRootNode](../winscript/reference/iremotedebugapplication-getrootnode.md)\).  
  
 구현에 [IDebugDocumentHelper::GetDebugApplicationNode](../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md), 단순히 반환 된 `IDebugApplication` 프로세스 디버그 관리자를 사용 하 여 처음에 만든.  
  
## IDebugDocumentHost 선택적 인터페이스  
 호스트의 구현을 제공할 수 있습니다는 [IDebugDocumentHost 인터페이스](../winscript/reference/idebugdocumenthost-interface.md) 를 사용 하 여 [IDebugDocumentHelper::SetDebugDocumentHost](../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md) 도우미 추가 제어를 제공 합니다.  다음은 몇 가지 주요 요점 호스트 인터페이스 할 수 있습니다.  
  
-   추가 텍스트를 사용 하 여 [IDebugDocumentHelper::AddDeferredText](../winscript/reference/idebugdocumenthelper-adddeferredtext.md) 호스트 바로 실제 문자를 제공 하지 않아도 되도록 합니다.  문자 정말 필요 하면 도우미 호출 [IDebugDocumentHost::GetDeferredText](../winscript/reference/idebugdocumenthost-getdeferredtext.md) 호스트.  
  
-   도우미에서 제공 되는 기본 구문 색상 표시를 무시 합니다.  도우미 호출 [IDebugDocumentHost::GetScriptTextAttributes](../winscript/reference/idebugdocumenthost-getscripttextattributes.md) 색의 기본 구현에서 호스트를 반환 하는 경우 폴백 문자의 범위를 확인 하려면 `E_NOTIMPL`.  
  
-   제어 알 수 없는 도우미로 구현 하 여 만든 문서 컨텍스트를 제공 [IDebugDocumentHost::OnCreateDocumentContext](../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md).  이 호스트를 기능을 기본 문서 컨텍스트 구현 재정의할 수 있습니다.  
  
-   문서에 대 한 파일 시스템에서 제공 하는 경로 이름.  일부 디버깅 Ui 편집 하 고 문서에 변경 내용을 저장 하는 사용자를 사용 합니다.  [IDebugDocumentHost::NotifyChanged](../winscript/reference/idebugdocumenthost-notifychanged.md)문서를 저장 한 후 호스트에 알리기 위해 호출 됩니다.  
  
## 참고 항목  
 [액티브 스크립트 디버깅 개요](../winscript/active-script-debugging-overview.md)