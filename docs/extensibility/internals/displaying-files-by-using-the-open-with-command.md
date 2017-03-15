---
title: "파일 열기 명령을 사용 하 여 사용 하 여 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 형식, 연결 프로그램 명령 지원"
  - "열기 명령"
  - "지 속성, 연결 프로그램 명령 지원"
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 파일 열기 명령을 사용 하 여 사용 하 여 표시
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트를 IDE를 표시 하도록 요청할 수 있습니다는  **와** 대화 상자.  이 요청을 표준 편집기의 선택 된 파일을 열려면 확인입니다.  다음 단계는이 프로세스에 설명 합니다.  
  
1.  프로젝트 통화 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, ose\_useopenwithdialog에 대 한 값을 지정 하는 `OSEOpenDocEditor` 매개 변수.  
  
2.  문서의 파일 확장명을 기준으로, IDE 지정한 문서의 레지스트리 있습니다 나열 된 어떤 편집기를 열어 결정 하 고이 정보를 표시를  **를** 대화 상자.  
  
    > [!NOTE]
    >  프로젝트에 포함 해야 합니다 내장 편집기는  **와** 대화 상자와 같은 각 편집기에 대 한 편집기 팩터리를 등록 해야 합니다.  내장 편집기 에서만 작동 하는 특정 유형의 구현에 적용 하는 프로젝트와 함께 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드가 있습니다.  IDE 기본 제공 편집기 팩터리를 코어 텍스트 편집기 및 바이너리 편집기에 있습니다.  또한 IDE 편집기 팩터리 인스턴스를 각 등록 된 Windows 파일 연결을 만듭니다.  이러한 파일의 예로 Microsoft Word입니다.  
  
3.  항목을 선택 하는 즉시 해당  **와** 대화 상자에서 다음 IDE를 호출 하 여 문서를 엽니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드.  자세한 내용은 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)를 참조하십시오.  
  
## 참고 항목  
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [파일 열기 명령을 사용 하 여 파일을 표시 합니다.](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)