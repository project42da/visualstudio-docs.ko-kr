---
title: "참조 페이지, 프로젝트 디자이너(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ProjectPropertiesReference"
  - "vb.ProjectPropertiesUnusedReference"
  - "vb.ProjectPropertiesReferencePaths"
helpviewer_keywords: 
  - "프로젝트 디자이너의 참조 페이지"
  - "프로젝트 디자이너, 참조 페이지"
  - "사용하지 않는 참조 대화 상자"
ms.assetid: 5a47c595-e084-401c-86e1-74e0bf74fd86
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 참조 페이지, 프로젝트 디자이너(Visual Basic)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**프로젝트 디자이너**의 **참조** 페이지를 사용하여 프로젝트의 참조, 웹 참조 및 가져온 네임스페이스를 관리할 수 있습니다.  프로젝트는 COM 구성 요소, XML Web services, .NET Framework 클래스 라이브러리나 어셈블리 또는 기타 클래스 라이브러리에 대한 참조를 포함할 수 있습니다.  참조 사용에 대한 자세한 내용은 [프로젝트의 참조 관리](../../ide/managing-references-in-a-project.md)를 참조하십시오.  
  
 액세스 하는  **참조** 페이지에서 프로젝트 노드를 선택 \(않습니다는  **솔루션** 노드\)에서  **솔루션 탐색기**.  다음 선택  **프로젝트**,  **속성** 메뉴 모음.  프로젝트 디자이너가 나타나면 클릭 하 여  **참조** 탭.  
  
## UI 요소 목록  
 다음 옵션을 사용하여 프로젝트에서 참조 및 가져온 네임스페이스를 선택하거나 제거할 수 있습니다.  
  
 **사용하지 않는 참조**  
 액세스 하려면이 단추를 클릭 하 여  **사용 하지 않는 참조** 대화 상자.  
  
 **사용하지 않는 참조** 대화 상자를 사용하면 프로젝트에 포함되어 있으나 실제로 코드에 의해 사용되지 않는 참조를 제거할 수 있습니다.  나열 하는 표를 포함의  **참조 이름**,  **경로**를 사용 하지 않는 네임 스페이스 참조를 프로젝트에 대 한 기타 정보.  프로젝트에서 제거하려는 네임스페이스 참조를 표에서 선택하고 **제거**를 클릭합니다.  
  
 **참조 경로**  
 액세스 하려면이 단추를 클릭 하 여  **참조 경로** 대화 상자.  
  
> [!NOTE]
>  프로젝트 시스템 어셈블리 참조가 발견 되 면 시스템에 대 한 참조 다음 순서 대로 다음 위치에서 확인 합니다.  
>   
>  1.  프로젝트 폴더입니다.  프로젝트 폴더의 파일에  **솔루션 탐색기** 때  **에서 모든 파일 표시** 적용 되지 않습니다.  
> 2.  지정 된 폴더의  **참조 경로** 대화 상자.  
> 3.  파일에서 표시 되는 폴더는  **참조 추가** 대화 상자.  
> 4.  프로젝트의 obj 폴더입니다.  \(프로젝트에 COM 참조를 추가 하면 하나 이상의 어셈블리가 프로젝트의 obj 폴더에 추가할 수 있습니다.\)  
  
 **참조**  
 이 목록에서는 프로젝트에서 사용하는 참조 및 사용하지 않는 참조를 모두 보여 줍니다.  
  
 **Add**  
 이 단추를 클릭하여 참조 또는 웹 참조를 **참조** 목록에 추가할 수 있습니다.  
  
 **참조 추가** 대화 상자를 사용하여 프로젝트에 참조를 추가하려면 참조를 선택합니다.  
  
 **웹 참조 추가** 대화 상자를 사용하여 프로젝트에 웹 참조를 추가하려면 웹 참조를 선택합니다.  
  
 **Remove**  
 **참조** 목록에서 하나 이상의 참조를 선택한 다음 이 단추를 클릭하여 해당 참조를 삭제할 수 있습니다.  
  
 **웹 참조 업데이트**  
 **참조** 목록에서 웹 참조를 선택하고 이 단추를 클릭하여 해당 웹 참조를 업데이트할 수 있습니다.  
  
 **가져온 네임스페이스**  
 이 상자에 사용자 고유의 네임스페이스를 입력하고 **사용자 가져오기 추가**를 클릭하여 해당 네임스페이스를 네임스페이스 목록에 추가할 수 있습니다.  
  
 사용자가 가져온 네임스페이스에 대해 별칭을 만들 수 있습니다.  이 작업을 수행하려면 *alias*\=*namespace* 형식으로 별칭과 네임스페이스를 입력합니다.  이렇게 하면 `Http= MyOrg.ObjectLib.Internet.WebRequestMethods.Http`에서와 같이 긴 네임스페이스를 사용하려는 경우에 편리합니다.  
  
 **사용자 가져오기 추가**  
 이 단추를 클릭하면 **가져온 네임스페이스** 상자에 지정된 네임스페이스를 가져온 네임스페이스의 목록에 추가할 수 있습니다.  이 단추는 지정된 네임스페이스가 아직 목록에 포함되지 않은 경우에만 활성화됩니다.  
  
 **네임스페이스 목록**  
 이 목록에서는 사용 가능한 모든 네임스페이스를 보여 줍니다.  프로젝트에 포함된 네임스페이스에 대한 확인란은 선택되어 있습니다.  
  
 **사용자 가져오기 업데이트**  
 네임스페이스 목록에서 사용자 지정 네임스페이스를 선택하고 **가져온 네임스페이스** 상자에서 대체할 이름을 입력한 다음 이 단추를 클릭하여 새 네임스페이스로 변경합니다.  이 단추는 선택된 네임스페이스가 **사용자 가져오기 추가** 단추를 사용하여 목록에 추가한 네임스페이스인 경우에만 활성화됩니다.  추가할 수 있는 항목은 다음과 같습니다.  
  
-   <xref:System.Math?displayProperty=fullName> 등의 클래스 또는 네임스페이스  
  
-   별칭이 지정된 `VB=Microsoft.VisualBasic` 등의 가져오기  
  
-   `<xmlns:xsl="http://www.w3.org/1999/XSL/Transform">` 등의 XML 네임스페이스  
  
## 참고 항목  
 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [방법: 가져온 네임스페이스 추가 또는 제거\(Visual Basic\)](../../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md)   
 [NIB: Add Web Reference Dialog Box](http://msdn.microsoft.com/ko-kr/bdf05776-c591-40af-bfd7-e1e2aa1e87b5)   
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)