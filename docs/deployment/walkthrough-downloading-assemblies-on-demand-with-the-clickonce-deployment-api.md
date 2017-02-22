---
title: "연습: ClickOnce 배포 API에서 요청 시 어셈블리 다운로드 | Microsoft Docs"
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
  - "어셈블리, 다운로드[ClickOnce]"
  - "ClickOnce 배포, 요청 시 다운로드"
  - "요청 시 어셈블리, ClickOnce"
ms.assetid: d20e2789-8621-4806-b5b7-841122da1456
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 연습: ClickOnce 배포 API에서 요청 시 어셈블리 다운로드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 포함된 모든 어셈블리는 응용 프로그램을 처음 실행할 때 다운로드됩니다.  그러나 응용 프로그램의 특정 부분은 그 사용자가 많지 않을 수 있습니다.  이 경우 해당 형식 중 하나를 만들 때만 어셈블리를 다운로드하도록 설정할 수도 있습니다.  다음 연습에서는 응용 프로그램의 특정 어셈블리를 "선택적"인 것으로 표시하는 방법과 CLR\(공용 언어 런타임\)에서 요청할 때 <xref:System.Deployment.Application> 네임스페이스의 클래스를 사용하여 이러한 어셈블리를 다운로드하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 절차를 사용하려면 응용 프로그램을 완전 신뢰 수준에서 실행해야 합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소 중 하나가 필요합니다.  
  
-   Windows SDK입니다.  Microsoft 다운로드 센터에서 Windows SDK를 다운로드할 수 있습니다.  
  
-   Visual Studio  
  
## 프로젝트 만들기  
  
#### 요청 시 어셈블리를 사용하는 프로젝트를 만들려면  
  
1.  이름이 ClickOnceOnDemand인 디렉터리를 만듭니다.  
  
2.  Windows SDK 명령 프롬프트나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 프롬프트를 엽니다.  
  
3.  ClickOnceOnDemand 디렉터리로 이동합니다.  
  
4.  다음 명령을 사용하여 공개\/개인 키 쌍을 생성합니다.  
  
    ```  
    sn -k TestKey.snk  
    ```  
  
5.  메모장이나 기타 텍스트 편집기를 사용하여 `Message`라는 속성 하나가 있는 `DynamicClass`라는 클래스를 정의합니다.  
  
     [!code-vb[ClickOnceLibrary#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]
     [!code-cs[ClickOnceLibrary#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]  
  
6.  사용하는 언어에 따라 이 텍스트를 `ClickOnceLibrary.cs` 또는 `ClickOnceLibrary.vb`라는 파일로 ClickOnceOnDemand 디렉터리에 저장합니다.  
  
7.  파일을 어셈블리로 컴파일합니다.  
  
    ```c#  
    csc /target:library /keyfile:TestKey.snk ClickOnceLibrary.cs  
    ```  
  
    ```vb#  
    vbc /target:library /keyfile:TestKey.snk ClickOnceLibrary.vb  
    ```  
  
8.  어셈블리에 대해 공개 키 토큰을 가져오려면 다음 명령을 사용합니다.  
  
    ```  
    sn -T ClickOnceLibrary.dll  
    ```  
  
9. 텍스트 편집기에서 새 파일을 만들고 다음 코드를 입력합니다.  이 코드는 필요할 때 ClickOnceLibrary 어셈블리를 다운로드하는 Windows Forms 응용 프로그램을 만듭니다.  
  
     [!code-cs[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/CSharp/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.cs)]
     [!code-vb[ClickOnceOnDemandCmdLine#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api_2.vb)]  
  
10. 이 코드에서 <xref:System.Reflection.Assembly.LoadFile%2A> 호출을 찾습니다.  
  
11. `PublicKeyToken`을 앞서 검색한 값으로 설정합니다.  
  
12. 파일을 `Form1.cs` 또는 `Form1.vb`로 저장합니다.  
  
13. 다음 명령을 사용하여 파일을 실행 파일로 컴파일합니다.  
  
    ```c#  
    csc /target:exe /reference:ClickOnceLibrary.dll Form1.cs  
    ```  
  
    ```vb#  
    vbc /target:exe /reference:ClickOnceLibrary.dll Form1.vb  
    ```  
  
## 선택적 어셈블리로 표시  
  
#### MageUI.exe를 사용하여 ClickOnce 응용 프로그램에서 어셈블리를 선택적인 것으로 표시하려면  
  
1.  [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)의 설명에 따라 MageUI.exe를 사용하여 응용 프로그램 매니페스트를 만듭니다.  응용 프로그램 매니페스트에 대해 다음 설정을 사용합니다.  
  
    -   응용 프로그램 매니페스트의 이름을 `ClickOnceOnDemand`로 지정합니다.  
  
    -   **파일** 페이지의 ClickOnceLibrary.dll 행에서 **파일 형식** 열을 **없음**으로 설정합니다.  
  
    -   **파일** 페이지의 ClickOnceLibrary.dll 행에서 **그룹** 열에 `ClickOnceLibrary.dll`을 입력합니다.  
  
2.  [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)의 설명에 따라 MageUI.exe를 사용하여 배포 매니페스트를 만듭니다.  배포 매니페스트에 대해 다음 설정을 사용합니다.  
  
    -   배포 매니페스트의 이름을 `ClickOnceOnDemand`로 지정합니다.  
  
## 새 어셈블리 테스트  
  
#### 요청 시 어셈블리를 테스트하려면  
  
1.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 웹 서버에 업로드합니다.  
  
2.  웹 브라우저에 배포 매니페스트의 URL을 입력하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 통해 배포된 응용 프로그램을 시작합니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 `ClickOnceOnDemand`를 호출하고 adatum.com의 루트 디렉터리에 이를 업로드하는 경우 URL은 다음과 같습니다.  
  
    ```  
    http://www.adatum.com/ClickOnceOnDemand/ClickOnceOnDemand.application  
    ```  
  
3.  주 폼이 나타나면 <xref:System.Windows.Forms.Button>을 누릅니다.  "Hello, World\!"라는 문자열이 메시지 상자 창에 나타나야 합니다.  
  
## 참고 항목  
 <xref:System.Deployment.Application.ApplicationDeployment>