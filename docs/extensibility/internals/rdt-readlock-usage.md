---
title: RDT_ReadLock 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7fda2fbb4a4b03dff9d677d9c7581a4138d9fcf7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="rdtreadlock-usage"></a>RDT_ReadLock 사용

<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> Visual Studio IDE에서 현재 열려 있는 모든 문서의 목록인에 실행 중인 문서 테이블 RDT (), 문서를 잠그기 위한 논리를 제공 하는 플래그가입니다. 이 플래그는 문서를 열 때 및 사용자 인터페이스에서 표시 되거나 메모리에서 켜지 열린 문서 인지를 결정 합니다.

일반적으로 사용 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 다음 중 하나가 충족 될 경우:

- 문서를 시각적으로 열 하려면 읽기 전용 아직 되지 않은 설정 하는 것 이지만 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 것을 소유 해야 합니다.

- 사용자를 시각적으로 연 하지 사용자 UI에 표시 하 고 닫습니다 하려고 하기 전에 문서를 저장 하 라는 메시지가 표시 하려는 경우.

## <a name="how-to-manage-visible-and-invisible-documents"></a>표시 되 고 표시 되지 않는 문서를 관리 하는 방법

사용자가 ui에서 문서를 열면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 문서에 대 한 소유자를 설정 해야 및 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 플래그를 설정 해야 합니다. 없는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 소유자를 설정할 수 있습니다, 다음 문서를 클릭할 때 저장 되지 것입니다 **모두 저장** 또는 IDE를 닫습니다. 이 의미 하는 경우는 문서가 열려 있지 않으면 시각적으로 메모리에서 수정 되 고 사용자가 종료 시 문서를 저장 하 라는 메시지가 표시 하거나 패키지가 저장 **모두 저장** 을 선택 하면 아니라면 `RDT_ReadLock` 사용할 수 없습니다. 를 대신 사용 해야는 `RDT_EditLock` 등록 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> 때는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER> 플래그입니다.

## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock 및 문서 수정

이전에 언급 된 플래그는 문서를 여는 보이지 않는 양보할 나타냅니다 해당 `RDT_EditLock` 에 표시 되는 문서는 사용자가 열릴 때 **참조 하시기 바랍니다**합니다. 이 경우 사용자가가 표시는 **저장** 때 메시지를 표시에서는 표시 되 **참조 하시기 바랍니다** 닫혀 있습니다. `Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel` 사용 하는 구현의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager> 경우에 서비스 작동 하는 처음에 `RDT_ReadLock` (즉, 문서를 열 때 하지 시각적으로 정보를 구문 분석)를 수행 합니다. 나중 문서를 수정 해야 하는 경우 잠금을로 업그레이드 약한 **RDT_EditLock**합니다. 표시 되는 다음 문서를 열 경우 **참조 하시기 바랍니다**, `CodeModel`의 약한 `RDT_EditLock` 해제 됩니다.

닫은 다음는 **참조 하시기 바랍니다** 를 선택 하 고 **아니요** 열려 있는 문서를 저장할지 묻는 메시지가 나타나면 하면 `CodeModel` 구현 문서에 있는 모든 정보를 삭제 하 고 다시 열립니다는 문서에서 디스크 켜지 다음에 문서에 자세한 정보가 필요 합니다. 이 동작에 미묘한은 사용자가 열 인스턴스는 **참조 하시기 바랍니다** 수정 보이지 않는 열린 문서의 닫고 한 다음 선택 **아니요** 문서를 저장 하 라는 메시지가 나타나면 합니다. 이 경우 문서에는 `RDT_ReadLock`, 다음 문서 실제로 닫히지 것입니다 및 수정된 된 문서 열린 채로 메모리에서 켜지 하지 문서를 저장 하는 사용자를 선택 합니다.

문서를 여는 보이지 않는 약한을 사용 하는 경우 `RDT_EditLock`, 사용자가 문서를 시각적으로 열 때 다른 잠금이 보유 되지 잠금의 생성 합니다. 사용자가 닫을 때는 **참조 하시기 바랍니다** 를 선택 하 고 **아니요** 문서를 저장 하는 메시지가 표시 되 면 다음 문서 닫아야 메모리에서 합니다. 즉, RDT 추적할 이벤트를이 항목에 대 한 보이지 않는 클라이언트가 수신 해야 합니다. 필요한 경우 문서는 다음에 문서 다시 열어야 합니다.