---
title: "파일 열기 명령을 사용 하 여 파일을 표시 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 형식, 파일 열기 명령 지원"
  - "파일 열기 명령"
  - "지 속성, 파일 열기 명령 지원"
ms.assetid: 4fff0576-b2f3-4f17-9769-930f926f273c
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 파일 열기 명령을 사용 하 여 파일을 표시 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 단계는 IDE를 처리 하는 방법을 설명는  **파일 열기** 명령을 사용할 수 있는  **파일** 메뉴에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  단계도 프로젝트가이 명령으로 시작 된 호출에 응답 해야 합니다 방법을 설명 합니다.  
  
 사용자를 클릭할 때는  **파일 열기** 에  **파일** 메뉴에서 파일을 선택 하 고는  **파일 열기** 대화 상자에서 다음 프로세스가 발생 합니다.  
  
1.  실행 중인 문서의 표를 사용 하 여 IDE 파일 프로젝트에서 열려 있는지 확인 합니다.  
  
    -   파일이 열려 있는 경우 IDE 창 resurfaces.  
  
    -   파일이 열려 있지 않은 경우 IDE를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> 프로젝트 파일을 열 수를 확인 하려면 각 프로젝트를 쿼리 합니다.  
  
        > [!NOTE]
        >  프로젝트 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A>, 프로젝트 열립니다 파일에 수준을 나타내는 우선 순위 값을 입력 합니다.  우선 순위 값에 제공 되는 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형입니다.  
  
2.  각 프로젝트에 우선 순위와 중요도 나타내는 응답 프로젝트 파일을 여는 중에 배치 됩니다.  
  
3.  다음 조건에 IDE를 사용 하 여 프로젝트 파일을 엽니다 확인 합니다.  
  
    -   가장 높은 우선 순위 \(DP\_Intrinsic\)에 응답 하는 프로젝트 파일을 엽니다.  이 우선 순위를 둘 이상의 프로젝트를 응답 하는 경우 응답 하는 첫 번째 프로젝트 파일을 엽니다.  
  
    -   프로젝트 응답 하지 않습니다 경우 우선 순위가 가장 높은 \(DP\_Intrinsic\) 그러나 모든 프로젝트 응답 같은, 낮은 우선 순위를 가진 활성 프로젝트 파일을 엽니다.  활성 프로젝트인 경우 응답 하는 첫 번째 프로젝트 파일을 엽니다.  
  
    -   프로젝트가 파일 \(DP\_Unsupported\)의 소유권을 주장 하는 경우 기타 파일 프로젝트에서 파일을 엽니다.  
  
         기타 파일 프로젝트의 인스턴스를 만든 경우 프로젝트는 항상 DP\_CanAddAsExternal 값으로 응답 합니다.  이 값은 프로젝트 파일을 열 수 있습니다 나타냅니다.  이 프로젝트는 다른 프로젝트에 열려 있는 파일을 저장할 수 있습니다.  이 프로젝트에 있는 항목의 목록을 유지 되지 않습니다. 이 프로젝트를 볼 수  **솔루션 탐색기** 때이 파일을 열 때만 사용 됩니다.  
  
         파일을 열 수 있는 기타 파일 프로젝트에 나타나지 않는 경우 인스턴스는 프로젝트를 만들었습니다.  이 경우 IDE 기타 파일 프로젝트의 인스턴스를 만들고 프로젝트 파일을 열 수를 지정 합니다.  
  
4.  IDE는 프로젝트 파일을 엽니다 확인 하는 즉시이 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> 메서드는 프로젝트의.  
  
5.  프로젝트에는 다음 파일을 프로젝트 고유 편집기 또는 표준 편집기를 사용 하 여 열 수가 있습니다.  자세한 내용은 각각 [방법: 프로젝트에 특정 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md) 및 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)을 참조하십시오.  
  
## 참고 항목  
 [파일 열기 명령을 사용 하 여 사용 하 여 표시](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트에 특정 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../../extensibility/how-to-open-standard-editors.md)