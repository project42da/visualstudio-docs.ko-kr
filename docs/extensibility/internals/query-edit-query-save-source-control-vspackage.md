---
title: 쿼리 (소스 제어 VSPackage) 저장 쿼리 편집 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- QEQS events
- Query Edit Query Save events
- source control packages, Query Edit Query Save events
ms.assetid: c360d2ad-fe42-4d65-899d-d1588cc8a322
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bf4fd74544e0646a84e4fdc37f35ba84b301f693
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="query-edit-query-save-source-control-vspackage"></a>쿼리 (소스 제어 VSPackage) 저장 쿼리 편집
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 편집기에 쿼리 편집 쿼리 저장 (QEQS) 이벤트 브로드캐스트할 수 있습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 스텁 QEQS 이벤트의 받는 사람 있도록 QEQS 서비스를 구현 합니다. 이러한 이벤트는 다음 현재 소스 제어 VSPackage에 위임 됩니다. VSPackage 구현 현재 소스 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 해당 메서드. 메서드는 `IVsQueryEditQuerySave2` 인터페이스는 일반적으로 문서를 저장 하기 전에 즉시 및 처음으로 문서를 편집 하는 바로 전에 호출 됩니다.  
  
## <a name="queryeditquerysave-events"></a>QueryEditQuerySave 이벤트  
 소스 제어 VSPackage를 구현 하 여 QEQS 이벤트를 처리 해야 합니다는 `IVsQueryEditQuerySave2` 인터페이스와 필요한 메서드. 다음은 최소한 VSPackage 구현 해야 하는 두 가지 방법에 대 한 간단한 설명입니다. 소스 제어 모델의 논리에 따라 실제 구현 해야 합니다.  
  
### <a name="queryeditfiles-method"></a>QueryEditFiles 메서드  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 프로젝트 또는 편집기 파일을 수정 하려고 할 때 호출 됩니다. 이 메서드를 호출 하는 것이 이상적 *전에* 파일이 수정 되 고은 파일을 저장 하는 경우. 호출 되 면는 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드 소스 제어에서 지정 된 파일 인지 여부, 체크 아웃 하는 데 필요한 여부 및 로드 하는지 여부를 확인 합니다. 상황 파일을 편집할 수 없도록 방지 하는 경우는 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드 편집을 취소 호출 프로그램에 알려 줍니다. 또한 호출 모드를 지정 하려면 호출자에 대 한도 가능 합니다. "자동" 모드에서이 메서드 모든 UI에 표시 되지는지 않습니다 하는 경우에 작업을 수행 합니다. UI를 피할 수 없는 경우는 문제를 표시 하는 플래그를 반환 합니다.  
  
 트랜잭션 방식으로; 메서드 즉, 단일 파일에서 편집이 취소 되는 모든 파일에 대 한 편집이 취소 됩니다. 반대로, 편집이 허용 되는 경우 모든 파일에 대해 허용 됩니다. 이 메서드는 파일의 지정된 된 집합에 대 한 한 번만 편집할 수 있습니다, 동일한 파일 집합에 대 한 후속 호출에서 편집 허용 항상 해야 합니다. 파일, 저장, 닫히고; 다시 로드 될 때까지 허용 편집 루프 계속 해당 특성 (속성)이 변경 될 때까지 또는 소스 제어 패키지 변경 될 때까지 합니다. 구현에서 고려 하는 경우는 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드 여러 파일을 특수 한 파일, 사용자, / 메모리 내 편집을 취소 합니다.  
  
### <a name="querysavefiles-method"></a>QuerySaveFiles 메서드  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> 프로젝트 또는 편집기 파일 집합을 저장 해야 할 때 호출 됩니다. 호출 되 면는 `IVsQueryEditQuerySave2::QuerySaveFiles` 지정 된 파일은 읽기 전용 및이 든 상관 없이 소스 제어에서 메서드를 확인 합니다. 파일을 체크 아웃 해야 하는 경우 호출 소스 제어 패키지에 위임 됩니다. 경우 파일을 저장 하는 것을 차단할 경우는 `IVsQueryEditQuerySave2::QuerySaveFiles` 메서드 파일을 저장 하 여 편집기를 지시 해야 합니다. 과 마찬가지로 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드는 호출 모드를 지정 하려면 호출자에 게 있습니다. "자동" 모드에서이 메서드 모든 UI에 표시 되지는지 않습니다 하는 경우에 작업을 수행 합니다. UI를 피할 수 없는 경우는 문제를 표시 하는 플래그를 반환 합니다.  
  
 이 메서드는; 트랜잭션 방식으로 동작 해야 즉, 단일 파일에 저장이 취소 되는 모든 파일에 대 한 저장이 취소 됩니다. 반대로, 저장 허용 된 경우 모든 파일에 대 한 허용 되어야 합니다. 과 마찬가지로 `IVsQueryEditQuerySave2::QueryEditFiles` 메서드를 구현할 때 고려해 야 할 경우는 `IVsQueryEditQuerySave2::QuerySaveFiles` 메서드 여러 파일을 특수 한 파일, 사용자, / 메모리 내 편집을 취소 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>