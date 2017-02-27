---
title: "실행 중인 Document 테이블 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "읽기 잠금을"
  - "실행 중인 document 테이블 (RDT) IVsDocumentLockHolder 인터페이스"
  - "실행 중인 document 테이블 (RDT)"
  - "실행 중인 document 테이블 (RDT) 편집 잠금"
  - "문서 데이터 개체를 문서에 있는 표를 실행 합니다."
ms.assetid: bbec74f3-dd8e-48ad-99c1-2df503c15f5a
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# 실행 중인 Document 테이블
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE에는 실행 중인 document 테이블 \(RDT\) 라고 하는 내부 구조에 현재 열려 있는 모든 문서 목록을 유지 관리 합니다. 이 목록에는 이러한 문서 편집 현재는 여부에 관계 없이 메모리에 열려 있는 모든 문서 포함 됩니다. 문서는 주 프로젝트 파일 \(예를 들어.vcxproj 파일\) 또는 프로젝트 파일을 포함 하 여 유지 되는 모든 항목입니다.  
  
## 실행 중인 문서 테이블의 요소  
 실행 중인 document 테이블에서 다음 항목을 포함합니다.  
  
|요소|설명|  
|--------|--------|  
|문서 모니커|문서 데이터 개체를 고유 하 게 식별 하는 문자열입니다. 이 절대 파일 경로 \(예를 들어 C:\\MyProject\\MyFile\) 파일을 관리 하는 프로젝트 시스템에 대 한 것입니다. 이 문자열은 데이터베이스의 저장된 프로시저와 같은 파일 시스템 이외의 저장소에 저장 하는 프로젝트에도 사용 됩니다. 이 경우 프로젝트 시스템 인식 하 고 문서를 저장 하는 방법을 알아보려면 가능성이 있는 구문 분석할 수 있는 고유 문자열을 만들 수 있습니다.|  
|계층 구조 소유자|에 표시 된 대로 문서를 소유 하는 계층 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스입니다.|  
|항목 ID|계층 내에서 특정 항목에 대 한 항목 식별자입니다. 이 값은이 문서를 소유 하는 계층의 모든 문서에 고유 하지만이 값은 서로 다른 계층 전체에서 고유 해야 아닙니다.|  
|문서 데이터 개체|이 최소한 한 `IUnknown`<br /><br /> 이름입니다. IDE 초과 특정 개입 하지 않아도 `IUnknown` 사용자 지정 편집기의 문서 데이터 개체에 대 한 인터페이스입니다. 그러나 표준 편집기에 대 한 편집기의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 프로젝트에서 파일 지 속성 호출을 처리 하려면 인터페이스가 필요 합니다. 자세한 내용은 [표준 문서 저장](../../extensibility/internals/saving-a-standard-document.md)을 참조하세요.|  
|플래그|읽기 또는 편집 잠금을 적용 되는지 여부를 문서를 저장 하는지 여부를 제어 하는 플래그와 이런 식으로 RDT에 항목을 추가할 때 지정할 수 있습니다. 자세한 내용은 참조는 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 열거형입니다.|  
|잠금 수를 편집 합니다.|편집 잠금 수입니다. 편집 잠금 일부 편집기에 문서가 편집을 위해 열려 있는지를 나타냅니다. 편집 잠금 수가 0으로 바뀌면가 수정 된 경우 사용자 문서를 저장 하 라는 메시지가 됩니다. 예를 들어를 사용 하 여 편집기에서 문서를 열 때마다는 **새 창** 명령을 편집 잠금은 RDT에서 해당 문서에 대 한 추가 됩니다. 문서에서 설정에 대 한 편집 잠금을 계층 구조를가지고 있거나 항목 id입니다.|  
|읽기 잠금 수|읽기 잠금을의 개수입니다. 읽기 잠금은 마법사와 같은 몇 가지 메커니즘을 통해 문서를 읽고 있는지를 나타냅니다. 읽기 잠금 문서를 편집할 수 없는 함을 나타내는 동안는 RDT에서 활성 문서를 보유 합니다. 문서 계층 구조가 하지 않거나 항목 id입니다. 경우에 읽기 잠금을 설정할 수 있습니다. 이 기능 없이 모든 계층에서 소유 하는 문서는 RDT에 입력 하십시오 메모리에서 문서를 열 수 있습니다. 이 기능은 자주 사용 됩니다.|  
|잠금 소유자|인스턴스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다. 잠금 소유자는 편집기 외부에서 문서 열기 및 편집 하는 마법사와 같은 기능에 의해 구현 됩니다. 잠금 소유자 기능을 편집 잠금으로 아직 편집 중인 동안 닫히는에서 문서를 방지 하기 위해 문서에 추가할 수 있습니다. 일반적으로 편집 잠금을 문서 창 \(즉, 편집기\)에 추가 합니다.|  
  
 RDT의 각 항목에 고유한 계층 또는 프로젝트의 노드 중 하나에 해당 하는 일반적으로 항목 ID와 연결 합니다. 편집을 위해 제공 하는 모든 문서는 일반적으로 계층에서 담당 합니다. 어떤 프로젝트를 제어 하는 RDT에 입력 또는\-보다 정확 하 게\-계층 구조를 현재 편집 중인 문서 데이터 개체를 소유 합니다. 정보를 사용 하 여 RDT에서, IDE는 문서를 한 번에 둘 이상의 프로젝트에 의해 열 방지할 수 있습니다.  
  
 계층 구조에서 또한 데이터의 지 속성을 제어 하 고는 RDT에 정보를 사용 하 여 업데이트 된 **저장** 및 **이름으로 저장** 대화 상자. 사용자가 문서를 수정 하 고 다음 경계 선택는 **종료** 명령을 **파일** 메뉴 IDE 프롬프트를 사용 하 여는 **변경 내용 저장** 대화 상자를 프로젝트와 현재 수정 된 프로젝트 항목의 모든 표시 합니다. 따라서 사용자가 저장 하는 문서를 선택할 수 있습니다. 문서를 저장할 목록 \(즉, 포함 된 문서를 변경\)는 RDT에서 생성 됩니다. 참조 되는 모든 항목은 **변경 내용 저장** 응용 프로그램을 종료할 때 대화 상자는 RDT에서 레코드를 가져야 합니다. 문서 저장 되 고 저장 하는 방법에 대 한 사용자가 입력 하는 여부는 RDT 조정 각 문서에 대 한 플래그 항목에 지정 된 값을 사용 하 여 작업 합니다. RDT 플래그에 대 한 자세한 내용은 참조는 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 열거형입니다.  
  
## 편집 잠금과 읽기 잠금  
 편집 잠금과 읽기 잠금을 RDT에 상주 합니다. 문서 창 증가 및 감소 시킵니다 편집이 잠급니다. 따라서 사용자가 새 문서 창을 열면 편집 잠금 수가 증가 하나입니다. 편집 잠금 수가 0에 도달 하면 유지 하거나 관련된 문서에 대 한 데이터를 저장 하는 계층 신호 됩니다. 계층의 파일 또는 저장소에 있는 항목으로 유지 하는 포함 하 여 어떤 방식으로든 데이터를 저장할 수 있습니다. 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.LockDocument%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> 편집 잠금을 추가 하 고 읽기 잠금을, 인터페이스를 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnlockDocument%2A> 이러한 잠금을 제거 하는 방법입니다.  
  
 일반적으로 편집기에 대 한 문서 창 인스턴스화되면 창 프레임의 문서에 대 한 편집 잠금을 RDT에 자동으로 추가 합니다. 그러나 문서의 사용자 지정 보기를 만드는 경우 사용 하지 않는 표준 문서 창 \(즉,을 구현 하지 않습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 인터페이스\)를 직접 편집 잠금을 설정 해야 합니다. 예를 들어, 마법사, 편집기에서 열리지 않고 문서 편집 됩니다. 마법사와 비슷한 엔터티도 열리도록 문서 잠금에 대 한 순서로 이러한 엔터티를 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 인터페이스입니다. 호출 하 여 문서 잠금 소유자를 등록 하려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.RegisterDocumentLockHolder%2A> 메서드를 전달 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 구현 합니다. 이렇게 하면 문서 잠금 소유자는 RDT 추가 합니다. 문서 잠금 소유자를 구현 하기 위한 또 다른 시나리오는 특수 한 도구 창을 통해 문서를 열 경우입니다. 이 인스턴스에서 문서 닫기 도구 창을 사용할 수 없는 합니다. 그러나는 RDT에서 문서 잠금 소유자를 등록 하 여 IDE를 호출할 수의 사용자 구현을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder.CloseDocumentHolder%2A> 문서 닫기 메시지를 표시 하는 메서드.  
  
## 실행 Document 테이블의 다른 용도  
 IDE에서 다른 엔터티는 RDT를 사용 하 여 문서에 대 한 정보를 가져옵니다. 예를 들어 소스 제어 관리자를 사용 하 여는 RDT 지시 파일의 최신 버전을 가져온 후에 편집기에서 문서를 다시 로드 하는 시스템입니다. 이렇게 하려면 소스 제어 관리자 모두 열려 있는지 확인 하기 위해 RDT의 파일을 찾습니다. 인 경우 원본 제어 관리자가 먼저 확인 합니다 계층 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드. 프로젝트를 구현 하지 않는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드를 다음 소스 제어의 구현에 대 한 관리자 검사는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 문서 데이터 개체를 직접 메서드를 호출 합니다.  
  
 IDE를 사용 하 여는 RDT resurface \(앞으로 가져오기\)는 사용자는 해당 문서를 요청 하는 경우 열려 있는 문서입니다. 자세한 내용은 [파일 열기 명령을 사용 하 여 파일을 표시 합니다.](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)을 참조하세요. RDT에서 열려 있는 파일 인지를 확인 하려면 다음을 수행 하나입니다.  
  
-   항목이 열린 인지 알아보려면 문서 모니커 \(즉, 전체 문서 경로\)를 쿼리 합니다.  
  
-   계층 구조 또는 항목 ID를 사용 하 여 전체 문서 경로 대 한 프로젝트 시스템을 주고 다음 항목에서에서 조회는 RDT 받을 수 있습니다.  
  
## 참고 항목  
 [RDT\_ReadLock 사용](../../extensibility/internals/rdt-readlock-usage.md)   
 [지 속성 및 실행 Document 테이블](../../extensibility/internals/persistence-and-the-running-document-table.md)