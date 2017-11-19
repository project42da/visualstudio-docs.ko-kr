---
title: "연습: 시작 페이지에 사용자 지정 XAML 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 924a6e2640002bc47eb75c903c46b5a170a9c308
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-adding-custom-xaml-to-the-start-page"></a>연습: 사용자 지정 XAML 시작 페이지에 추가
이 연습에는 사용자 지정 Visual Studio 시작 페이지는 웹 브라우저를 포함 하는 방법을 보여 줍니다.  
  
## <a name="adding-custom-xaml"></a>XAML 사용자 정의 추가  
  
1.  시작 페이지의 지침에 따라 만들 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md)합니다.  
  
2.  MainWindow.xaml 파일에서 찾습니다는 \<표 > 섹션입니다.  
  
3.  추가 \<TabControl > 요소와 \<TabItem > 내에서 \< 표 > 요소를 다음 예제와 같이 합니다.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
4.  두 번째 추가 \<TabItem >와 \<단추 > 요소를 새 프로젝트를 엽니다.  
  
    ```xml  
    <Grid>  
        <TabControl>  
            <TabItem Header="MyButton" Height="Auto">  
                <Button Name="btnNewProj" Content="New Project"   
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
                    CommandParameter="File.NewProject" >  
                </Button>  
            </TabItem>  
            <TabItem Header="Bing" Height="Auto">  
                <Frame Source="http://www.bing.com" />  
            </TabItem>  
        </TabControl>  
    </Grid>  
    ```  
  
## <a name="testing-the-custom-start-page"></a>사용자 지정 시작 페이지를 테스트합니다.  
  
1.  F5 키를 누릅니다.  
  
     사용자 지정 시작 페이지가 설치 되어 있지만 선택 하지 않은 Visual Studio의 실험적 인스턴스가 열립니다.  
  
2.  Visual Studio의 실험적 인스턴스를 열고는 **도구 상자로 / 환경** 페이지.  
  
3.  선택 **시작**합니다. 에 **시작 페이지 사용자 지정** 목록에서.xaml 파일을 선택한 클릭 **확인**합니다.  
  
4.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
5.  클릭는 **Bing** 탭 합니다.  
  
     Bing 웹 페이지가 나타납니다.  
  
6.  클릭는 **MyButton** 탭 합니다.  
  
     표시 됩니다는 **MyProject** 열리는 단추는 **새 프로젝트** 대화입니다.  
  
7.  실험적 인스턴스를 닫습니다.  
  
## <a name="applying-the-custom-start-page"></a>사용자 지정 시작 페이지를 적용합니다.  
  
#### <a name="to-test-the-custom-start-page"></a>사용자 지정 시작 페이지를 테스트 하려면  
  
1.  **도구 / 옵션 / 환경**선택, **시작**합니다. 에 **시작 페이지 사용자 지정** 목록에서.xaml 파일을 선택한 클릭 **확인**합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이제 Visual Studio 시작 페이지에는 웹 브라우저 탭과 MyButton 탭이 표시 하는 탭 포함 되어 있습니다. 사용 하 여 다른 기능이 있는 사용자 지정 시작 페이지를 만들 수는 *코드 숨김* 모델에 표시 된 대로 사용자 지정.dll을 추가 하려면 [시작 페이지를 사용자 정의 컨트롤 추가](../extensibility/adding-user-control-to-the-start-page.md)합니다. 결과.vsix 파일을 게시 하 여 다른 사용자와 사용자 지정 시작 페이지를 공유할 수는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트 또는 다른 웹 사이트 또는 네트워크 공유 합니다. 자세한 내용은 참조 [배포 사용자 지정 시작 페이지](../extensibility/deploying-custom-start-pages.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)   
 [WPF 컨테이너 컨트롤](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)