---
title: "RDT_ReadLock 사용 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: e7575b914f0645882f3570bdbe29221f2f8130cc
ms.openlocfilehash: a8ea44ef2dea3b3c4ebd29cf95b1886e2028e2c3
ms.lasthandoff: 02/22/2017

---
# <a name="rdtreadlock-usage"></a>RDT_ReadLock 사용

<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>Visual Studio IDE에서 현재 열려 있는 모든 문서의 목록인에 실행 중인 문서 테이블 RDT (), 문서를 잠금에 대 한 논리를 제공 하는 플래그가입니다.</xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> 이 플래그는 문서를 열 때와 사용자 인터페이스에 표시 하거나 표시 하지 않고 메모리에 보관 된 문서 인지를 결정 합니다.

일반적으로 사용 합니다 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>다음 중 하나가 true 인 경우:</xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>

- 문서를 시각적으로 열고 하려는 경우 읽기 전용 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>그룹을 소유 해야 합니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 어떤 설정 아직 되지 않은 것 하지만

- 사용자를 시각적으로 연 하지 사용자 UI에 표시 하 고 닫습니다 하려고 하기 전에 문서를 저장 하 라는 메시지가 표시 하려는 경우.

## <a name="how-to-manage-visible-and-invisible-documents"></a>표시 되 고 보이지 않는 문서를 관리 하는 방법

사용자가 UI에 문서를 열면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>문서에 대 한 소유자를 설정 해야 및 <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS>플래그를 설정 해야 합니다.</xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS> </xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 없으면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>소유자를 설정할 수 있습니다, 다음 문서를 클릭할 때 저장 되지 것입니다 **모두 저장** 또는 IDE를 닫습니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 이 의미 하는 경우는 문서가 열려 있지 않으면 시각적으로 메모리 내에 수정 되 고 사용자가 종료 시 문서를 저장 하 라는 메시지가 표시 하거나 저장 하는 경우 **모두 저장** 를 선택 하면 `RDT_ReadLock` 사용할 수 없습니다. 대신 사용 해야는 `RDT_EditLock` 및 등록 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder>때는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER>플래그.</xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER> </xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder>

## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock 및 문서 수정

언급 한 이전 플래그는 문서를 여는 보이지 않는 필요할지 나타냅니다 그 `RDT_EditLock` 에 표시 되는 문서 사용자가 열 때 **참조 하시기 바랍니다**. 이 경우 사용자는가 표시는 **저장** 때 메시지를 표시에서는 표시 되 **참조 하시기 바랍니다** 닫힙니다. <xref:Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel>사용 하는 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager>서비스는 처음에 경우에 작동는 `RDT_ReadLock` (즉, 문서를 열 때 하지 시각적으로 정보를 구문 분석) 수행 합니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager></xref:Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel> 나중에 문서를 수정 해야 하는 경우 다음 잠금을으로 업그레이드 됩니다 약한 **RDT_EditLock**합니다. 표시 되에서 다음 문서를 열 경우 **참조 하시기 바랍니다**, `CodeModel`의 약한 `RDT_EditLock` 해제 됩니다.

닫은 다음는 **참조 하시기 바랍니다** 선택한 **No** 열려 있는 문서를 저장 하 라는 메시지가 나타나면 면 `CodeModel` 구현 문서에 있는 모든 정보를 삭제 하 고 닫았다가 다시 열거나 하지 디스크에서 문서 눈에 보이지 않게 다음에 문서에 자세한 정보가 필요 합니다. 이 동작에 주의 해야 사용자가 있는 인스턴스가 **참조 하시기 바랍니다** 보이지 않는 열린 문서의 수정 하 고, 닫고 선택한 다음 **No** 문서를 저장 하 라는 메시지가 나타나면 합니다. 여기서는 문서에는 `RDT_ReadLock`, 다음 문서 실제로 닫히지 것입니다 및 수정 된 문서 열린 채로 표시 하지 않고 메모리에는 사용자를 문서를 저장 하지 않도록 선택한 경우에 있습니다.

문서를 여는 보이지 않는 약한을 사용 하는 경우 `RDT_EditLock`, 사용자가 문서를 시각적으로 열 때 다른 잠금이 보유 되지 잠금을 생성 합니다. 사용자가 닫을 때는 **참조 하시기 바랍니다** 선택한 **No** 문서를 저장할 대화 상자가 나타나면 다음 문서를 닫아야 메모리에서. 즉, 보이지 않는 클라이언트 RDT 추적할 이벤트를이 항목에 대 한 수신 대기 해야 합니다. 다음에 문서는 필요한 경우 문서 다시 열어야 합니다.
