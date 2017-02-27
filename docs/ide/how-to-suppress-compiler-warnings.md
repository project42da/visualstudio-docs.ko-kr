---
title: "방법: 컴파일러 경고 표시 안 함 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31827b17-f933-413d-b28a-b19f903b64ca
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# 방법: 컴파일러 경고 표시 안 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

컴파일러 경고를 포함 하 여 원치 않는 하나 이상의 종류를 지정 하 여 빌드 로그에 혼잡 방지 수 있습니다.  예를 들어,이 기법은 일부를 검토할 수 있지만 보통, 자세히 또는 진단 빌드 로그의 자세한 정도 설정할 때 자동으로 생성 되는 정보 중 일부를 사용할 수 있습니다.  자세한 정도 대 한 자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](../ide/how-to-view-save-and-configure-build-log-files.md).  
  
### C\# 또는 F\#에 대 한 특정 경고를 표시 하지  
  
1.  **솔루션 탐색기**, 경고 프로젝트를 선택 합니다.  
  
2.  메뉴 모음에서 선택  **보기**,  **속성 페이지**.  
  
3.  선택 된  **빌드** 페이지입니다.  
  
4.  에  **표시 안 함 경고** 상자에서 세미콜론으로 구분 된 오류 코드를 표시 하지 않으려면 원하는 경고를 지정 하 고 솔루션을 다시 빌드합니다.  
  
### Visual C\+\+ 대 한 특정 경고를 표시 하지  
  
1.  **솔루션 탐색기**소스에서 경고를 표시 하려면 파일, 프로젝트를 선택 합니다.  
  
2.  메뉴 모음에서 선택  **보기**,  **속성 페이지**.  
  
3.  선택의  **구성 속성** 범주 선택의  **C\/c \+ \+** 범주를 다음 선택의  **고급** 페이지.  
  
4.  다음 단계 중 하나를 수행합니다.  
  
    -   에  **특정 경고 사용 안 함** 상자에서 세미콜론으로 구분 된 오류 코드를 표시 하지 않으려면 원하는 경고를 지정 합니다.  
  
    -   에  **특정 경고 사용 안 함** 상자에서 선택  **편집** 더 많은 옵션을 표시 합니다.  
  
5.  선택 된  **확인** 단추를 클릭 한 다음 솔루션을 다시 빌드합니다.  
  
## Visual Basic 대 한 경고 표시 안 함  
 특정 컴파일러 경고에 대 한 Visual Basic 프로젝트의.vbproj 파일을 편집 하 여 숨길 수 있습니다.  사용할 수도 있습니다는  [프로젝트 디자이너, 컴파일 페이지](../ide/reference/compile-page-project-designer-visual-basic.md) 범주에서 경고를 표시 합니다.  자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하십시오.  
  
#### Visual Basic 대 한 특정 경고를 표시 하지  
  
1.  **솔루션 탐색기**, 경고 프로젝트를 선택 합니다.  
  
2.  메뉴 모음에서 선택  **프로젝트**,  **프로젝트 언로드**.  
  
3.  **솔루션 탐색기**프로젝트에 대 한 바로 가기 메뉴를 열고 선택  **편집***ProjectName***.vbproj**.  
  
     프로젝트 파일이 코드 편집기에서 열립니다.  
  
4.  찾기는 `<NoWarn></NoWarn>` 중인 된 빌드 빌드 구성에서 요소입니다.  
  
     다음 예제는 `<NoWarn></NoWarn>` 에서 굵게 x86 플랫폼에서 디버그 빌드 구성 요소:  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn> </NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
5.  하나 이상의 경고 번호 값으로 추가 된 `<NoWarn>` 요소.  여러 개의 경고 번호를 지정 하는 경우에 다음 예제와 같이 쉼표로 구분 합니다.  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn>40059,42024</NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
6.  변경 내용을.vbproj 파일에 저장 합니다.  
  
7.  메뉴 모음에서 선택  **프로젝트**,  **프로젝트 다시 로드**.  
  
8.  메뉴 모음에서 선택  **빌드**,  **솔루션 다시 빌드**.  
  
     **출력** 창 더 이상 지정 된 경고를 표시 합니다.  
  
 자세한 내용은 [\/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)을 참조하십시오.  
  
## 참고 항목  
 [연습: 응용 프로그램 빌드](../ide/walkthrough-building-an-application.md)   
 [방법: 빌드 로그 파일 보기, 저장 및 구성](../ide/how-to-view-save-and-configure-build-log-files.md)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)