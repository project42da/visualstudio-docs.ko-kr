---
title: "연습: 시작 페이지 사용자 지정 XAML에 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 시작 페이지"
  - "xaml 시작 페이지"
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 연습: 시작 페이지 사용자 지정 XAML에 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에는 사용자 지정 Visual Studio 시작 페이지는 웹 브라우저를 포함 하는 방법을 보여 줍니다.  
  
## 사용자 지정 XAML을 추가합니다.  
  
1.  시작 페이지의 지침에 따라 만들 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md)합니다.  
  
2.  MainWindow.xaml 파일에서 \< 표 \> 섹션을 찾습니다.  
  
3.  다음 예제와 같이 \< 표 \> 요소 내의 \< TabItem \> 및 \< TabControl \> 요소를 추가 합니다.  
  
    ```xml  
    <Grid> <TabControl> <TabItem Header="Bing" Height="Auto"> <Frame Source="http://www.bing.com" /> </TabItem> </TabControl> </Grid>  
    ```  
  
4.  새 프로젝트를 열고 \< 단추 \> 요소와 두 번째 \< TabItem \>를 추가 합니다.  
  
    ```xml  
    <Grid> <TabControl> <TabItem Header="MyButton" Height="Auto"> <Button Name="btnNewProj" Content="New Project" Command="{x:Static vscom:VSCommands.ExecuteCommand}" CommandParameter="File.NewProject" > </Button> </TabItem> <TabItem Header="Bing" Height="Auto"> <Frame Source="http://www.bing.com" /> </TabItem> </TabControl> </Grid>  
    ```  
  
## 사용자 지정 시작 페이지를 테스트합니다.  
  
1.  F5 키를 누릅니다.  
  
     Visual Studio의 실험적 인스턴스에서 열리고, 사용자 지정 시작 페이지 선택 되지는 않고 설치 됩니다.  
  
2.  Visual Studio의 실험적 인스턴스를 열고는 **\/Options 도구 \/ 환경** 페이지입니다.  
  
3.  선택 **시작**합니다. 에 **시작 페이지 사용자 지정** 목록.xaml 파일을 선택 하 고 클릭 **확인**합니다.  
  
4.  에 **보기** 메뉴를 클릭 하 여 **시작 페이지**합니다.  
  
5.  클릭 하 고 **Bing** 탭 합니다.  
  
     Bing 웹 페이지 표시 되어야 합니다.  
  
6.  클릭 하 고 **MyButton** 탭 합니다.  
  
     표시 되어야는 **MyProject** 열리는 단추는 **새 프로젝트** 대화 합니다.  
  
7.  실험적 인스턴스를 닫습니다.  
  
## 사용자 지정 시작 페이지를 적용합니다.  
  
#### 사용자 지정 시작 페이지를 테스트 하려면  
  
1.  **도구 \/ 옵션 \/ 환경**, 선택, **시작**합니다. 에 **시작 페이지 사용자 지정** 목록.xaml 파일을 선택 하 고 클릭 **확인**합니다.  
  
## 다음 단계  
 이제 Visual Studio 시작 페이지에는 웹 브라우저 탭과 MyButton 탭이 표시 하는 탭 포함 되어 있습니다. 사용 하 여 다른 기능을 포함 하는 사용자 지정 시작 페이지를 만들 수는 *코드 숨김* 모델에 표시 된 대로 사용자 지정.dll을 추가 하려면 [시작 페이지에 사용자 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)합니다. 결과.vsix 파일을 게시 하 여 다른 사용자와 사용자 지정 시작 페이지를 공유할 수는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트 또는 다른 웹 사이트 또는 네트워크 공유입니다. 자세한 내용은 [사용자 지정 시작 페이지를 배포합니다.](../extensibility/deploying-custom-start-pages.md)을 참조하세요.  
  
## 참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [WPF 컨테이너 컨트롤](http://msdn.microsoft.com/ko-kr/a0177167-d7db-4205-9607-8ae316952566)