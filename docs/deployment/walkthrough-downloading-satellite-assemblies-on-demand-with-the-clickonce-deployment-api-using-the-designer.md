---
title: "연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 전역화"
  - "ClickOnce 배포, 지역화"
  - "ClickOnce, 요청 시 다운로드"
  - "지역화, Windows Forms"
  - "연습, 지역화"
  - "Windows Forms, 전역화"
  - "Windows Forms, 지역화"
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

위성 어셈블리를 사용하면 Windows Forms 응용 프로그램을 여러 문화권에 맞게 구성할 수 있습니다.  *위성 어셈블리*는 응용 프로그램의 기본 문화권 이외의 문화권을 위한 응용 프로그램 리소스가 포함된 어셈블리입니다.  
  
 [ClickOnce 응용 프로그램 지역화](../deployment/localizing-clickonce-applications.md)에서 설명한 대로 동일한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 내에 여러 문화권을 위한 여러 위성 어셈블리를 포함할 수 있습니다.  기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 단일 클라이언트에 하나의 위성 어셈블리만 필요한 경우라도 배포의 모든 위성 어셈블리를 클라이언트 컴퓨터에 다운로드합니다.  
  
 이 연습에서는 위성 어셈블리를 선택적 항목으로 표시하고 클라이언트 컴퓨터의 현재 문화권 설정에 필요한 어셈블리만 다운로드하는 방법을 설명합니다.  
  
> [!NOTE]
>  테스트를 위해 다음 코드 예제에서는 프로그래밍 방식으로 문화권을 `ja-JP`로 설정합니다.  이 코드를 프로덕션 환경에 맞게 조정하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 "다음 단계" 섹션을 참조하세요.  
  
### 위성 어셈블리를 선택 항목으로 표시하려면  
  
1.  프로젝트를 빌드합니다.  이렇게 하면 지역화할 모든 문화권에 대한 위성 어셈블리가 생성됩니다.  
  
2.  솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
3.  **게시** 탭을 클릭하고 **응용 프로그램 파일**을 클릭합니다.  
  
4.  **모든 파일 표시** 확인란을 선택하여 위성 어셈블리를 표시합니다.  기본적으로 모든 위성 어셈블리는 배포에 포함되고 이 대화 상자에 표시됩니다.  
  
     위성 어셈블리의 이름은 *isoCode*\\ApplicationName.resources.dll 형식입니다. 여기에서 *isoCode*는 RFC 1766 형식의 언어 식별자입니다.  
  
5.  각 언어 식별자에 대해 **다운로드 그룹** 목록에서 **새로 만들기...**를 클릭합니다.  다운로드 그룹 이름을 요청하는 메시지가 표시되면 언어 식별자를 입력합니다.  예를 들어 일본어 위성 어셈블리의 경우 다운로드 그룹 이름 `ja-JP`를 지정합니다.  
  
6.  **응용 프로그램 파일** 대화 상자를 닫습니다.  
  
### C\#에서 요청 시 위성 어셈블리를 다운로드하려면  
  
1.  Program.cs 파일을 엽니다.  솔루션 탐색기에서 이 파일을 표시하지 않으려면 프로젝트를 선택하고 **프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.  
  
2.  다음 코드를 사용하여 해당하는 위성 어셈블리를 다운로드하고 응용 프로그램을 시작합니다.  
  
     [!code-cs[ClickOnce.SatelliteAssemblies#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_1.cs)]  
  
### Visual Basic에서 요청 시 위성 어셈블리를 다운로드하려면  
  
1.  응용 프로그램에 대한 **속성** 창에서 **응용 프로그램** 탭을 클릭합니다.  
  
2.  탭 페이지 아래쪽에서 **응용 프로그램 이벤트 보기**를 클릭합니다.  
  
3.  ApplicationEvents.VB 파일의 시작 부분에 다음 가져오기를 추가합니다.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_2.vb)]  
  
4.  `MyApplication` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[ClickOnce.SatelliteAssembliesVB#2](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer_3.vb)]  
  
## 다음 단계  
 프로덕션 환경에서는 기본적으로 클라이언트 컴퓨터에 올바른 값이 설정되어 있으므로 <xref:System.Threading.Thread.CurrentUICulture%2A>를 특정 값으로 설정하는 줄을 코드 예제에서 제거해야 할 수 있습니다.  예를 들어 응용 프로그램이 일본어 클라이언트 컴퓨터에서 실행될 경우 <xref:System.Threading.Thread.CurrentUICulture%2A>는 기본적으로 `ja-JP`입니다.  응용 프로그램을 배포하기 전에 이 값을 프로그래밍 방식으로 설정하면 위성 어셈블리를 쉽게 테스트할 수 있습니다.  
  
## 참고 항목  
 [연습: ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)   
 [ClickOnce 응용 프로그램 지역화](../deployment/localizing-clickonce-applications.md)