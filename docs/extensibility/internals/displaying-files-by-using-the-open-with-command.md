---
title: "파일 열기 명령을 사용 하 여 표시 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed8a19ce0cfb6a7936d61ff7a5855498d2010359
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="displaying-files-by-using-the-open-with-command"></a>파일 열기 명령을 사용 하 여 표시
프로젝트를 표시 하려면 IDE를 요청할 수는 **프로그램** 대화 상자. 이 요청 라는 표준 편집기는 선택 항목에 있는 파일을 열 수입니다. 다음 단계는이 프로세스를 설명 합니다.  
  
1.  프로젝트를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, OSE_UseOpenWithDialog에 대 한 값을 지정 하는 `OSEOpenDocEditor` 매개 변수입니다.  
  
2.  문서의 파일 이름 확장명에 따라, IDE 레지스트리 수에 나열 된는 편집기에서 지정 된 문서를 열을 결정 하며이 정보에 표시 된 **연결** 대화 상자.  
  
    > [!NOTE]
    >  에 꼭 포함 되어야 하는 기본 편집기가 프로젝트에는 **프로그램** 이러한 각 편집기에 대 한 대화 상자 편집기 팩터리를 등록 해야 합니다. 구현에 적용 되는 프로젝트의 특정 형식과 함께 편집기 내장 함수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드. IDE에는 핵심 텍스트 편집기와 바이너리 편집기에 대 한 기본 제공 편집기 팩터리입니다. IDE는 또한 각 등록 된 Windows 파일 연결을 대신 하 여 편집기 팩터리의 인스턴스를 만듭니다. 이러한 파일의 예는 Microsoft Word입니다.  
  
3.  항목을 선택 하는 즉시는 **프로그램** 대화 상자에서 다음 IDE를 호출 하 여 문서를 엽니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드. 자세한 내용은 참조 [하는 방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [파일 열기 명령을 사용 하 여 파일을 표시 합니다.](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)