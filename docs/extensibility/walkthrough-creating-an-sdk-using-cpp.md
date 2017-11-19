---
title: "연습: c + +를 사용 하 여 SDK 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36ea793b-3832-41a1-b906-69e680ad5e1d
caps.latest.revision: "32"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bc30e3236f81f558f3794bb459f6da3edbdaa63d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-an-sdk-using-c"></a>연습: c + +를 사용 하 여 SDK 만들기
이 연습에는 네이티브 c + + 수학 라이브러리 SDK, SDK로는 VSIX Visual Studio Extension (), 패키지를 만들고 다음 앱을 만드는 데 사용 하는 방법을 보여 줍니다. 이 연습에서는 다음이 단계도 구분 됩니다.  
  
-   [네이티브 및 Windows 런타임 라이브러리를 만들려면](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createClassLibrary)  
  
-   [NativeMathVSIX 확장 프로젝트를 만들려면](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createVSIX)  
  
-   [클래스 라이브러리를 사용 하는 샘플 앱을 만들려면](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createSample)  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
##  <a name="createClassLibrary"></a>네이티브 및 Windows 런타임 라이브러리를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  템플릿 목록에서 확장 **Visual c + +**, **Windows 스토어**를 선택한 후는 **DLL (Windows 스토어 앱)** 서식 파일입니다. 에 **이름** 상자를 지정 `NativeMath`를 선택한 후는 **확인** 단추입니다.  
  
3.  다음 코드와 일치 하도록 NativeMath.h를 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#1](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_1.h)]  
  
4.  이 코드와 일치 하도록 NativeMath.cpp를 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_2.cpp)]  
  
5.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **솔루션 'NativeMath'**를 선택한 후 **추가**, **새 프로젝트**합니다.  
  
6.  템플릿 목록에서 확장 **Visual c + +**를 선택한 후는 **Windows 런타임 구성 요소** 템플릿. 에 **이름** 상자를 지정 `NativeMathWRT`를 선택한 후는 **확인** 단추입니다.  
  
7.  이 코드와 일치 하도록 Class1.h를 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_3.h)]  
  
8.  Class1.cpp이이 코드와 일치 하도록 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#4](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_4.cpp)]  
  
9. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
##  <a name="createVSIX"></a>NativeMathVSIX 확장 프로젝트를 만들려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **솔루션 'NativeMath'**를 선택한 후 **추가**, **새 프로젝트**합니다.  
  
2.  템플릿 목록에서 확장 **Visual C#**, **확장성**를 선택한 후 **VSIX 패키지**합니다. 에 **이름** 상자를 지정 **NativeMathVSIX**를 선택한 후는 **확인** 단추입니다.  
  
3.  VSIX 매니페스트 디자이너에 표시 되 면 닫습니다.  
  
4.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **source.extension.vsixmanifest**를 선택한 후 **코드 보기**합니다.  
  
5.  다음 XML을 사용 하 여 기존 XML 바꿉니다.  
  
    [!code-xml[CreatingAnSDKUsingCpp#6](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_6.xml)]

6.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **NativeMathVSIX** 프로젝트를 선택한 후 **추가**, **새 항목**합니다.  
  
7.  목록에서 **Visual C# 항목**를 확장 하 고 **데이터**를 선택한 후 **XML 파일**합니다. 에 **이름** 상자를 지정 `SDKManifest.xml`를 선택한 후는 **확인** 단추입니다.  
  
8.  이 XML을 사용 하 여 파일의 내용을 바꿉니다.  
  
     [!code-xml[CreatingAnSDKUsingCpp#5](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_5.xml)]  
  
9. **솔루션 탐색기**에 **NativeMathVSIX** 프로젝트에서이 폴더 구조를 만듭니다.  
  
    ```  
  
    \DesignTime  
          \CommonConfiguration  
                \Neutral  
                      \Include  
          \Debug  
                \x86  
    \Redist  
          \Debug  
                \x86  
    \References  
          \CommonConfiguration  
                \Neutral  
    ```  
  
10. **솔루션 탐색기**, 바로 가기 메뉴를 열고 **솔루션 'NativeMath'**를 선택한 후 **파일 탐색기에서 폴더 열기**합니다.  
  
11. **파일 탐색기**, \NativeMath\NativeMath.h, 복사 한 다음 **솔루션 탐색기**에 **NativeMathVSIX** 프로젝트는 \DesignTime\에 붙여 넣고 CommonConfiguration\Neutral\Include\ 폴더입니다.  
  
     \Debug\NativeMath\NativeMath.lib을 복사한 다음 \DesignTime\Debug\x86\ 폴더에 붙여 넣습니다.  
  
     \Debug\NativeMath\NativeMath.dll 복사한 \Redist\Debug\x86\ 폴더에 붙여 넣습니다.  
  
     DebugNativeMathWRTNativeMathWRT.dll 복사한 RedistDebugx86 폴더에 붙여 넣습니다.  
  
     DebugNativeMathWRTNativeMathWRT.winmd 복사한 ReferencesCommonConfigurationNeutral 폴더에 붙여 넣습니다.  
  
     DebugNativeMathWRTNativeMathWRT.pri 복사한 ReferencesCommonConfigurationNeutral 폴더에 붙여 넣습니다.  
  
12. \DesignTime\Debug\x86\ 폴더에 NativeMathSDK.props, 라는 텍스트 파일 만들고 그 안에 다음 마법사나 합니다.  
  
    [!code-xml[CreatingAnSDKUsingCpp#7](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_7.xml)]  
  
13. 메뉴 모음에서 **보기**, **다른 창**, **속성 창** (키보드: F4 키를 선택).  
  
14. **솔루션 탐색기**, 선택는 **NativeMathWRT.winmd** 파일입니다. 에 **속성** 창에서 변경 된 **빌드 작업** 속성을 **콘텐츠**, 바꾼 다음는 **VSIX에 포함** 속성 를 **True 이면**합니다.  
  
     이 프로세스를 반복는 **SimpleMath.pri** 파일입니다.  
  
     이 프로세스를 반복는 **NativeMath.Lib** 파일입니다.  
  
     이 프로세스를 반복는 **NativeMathSDK.props** 파일입니다.  
  
15. **솔루션 탐색기**, 선택는 **NativeMath.h** 파일입니다. 에 **속성** 창에서 변경 된 **VSIX에 포함** 속성을 **True**합니다.  
  
     이 프로세스를 반복는 **NativeMath.dll** 파일입니다.  
  
     이 프로세스를 반복는 **NativeMathWRT.dll** 파일입니다.  
  
     이 프로세스를 반복는 **SDKManifest.xml** 파일입니다.  
  
16. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
17. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **NativeMathVSIX** 프로젝트를 선택한 후 **파일 탐색기에서 폴더 열기**합니다.  
  
18. **파일 탐색기**, \bin\Debug\ 폴더를 탐색 하 고 NativeMathVSIX.vsix 설치를 시작 하려면 다음 실행 합니다.  
  
19. 선택 된 **설치** 단추 설치가 완료 되기를 기다린 후 다음 Visual Studio를 다시 시작 합니다.  
  
##  <a name="createSample"></a>클래스 라이브러리를 사용 하는 샘플 앱을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  템플릿 목록에서 확장 **Visual c + +**, **Windows 스토어**를 선택한 후 **비어 있는 앱**합니다. 에 **이름** 상자를 지정 **NativeMathSDKSample**를 선택한 후는 **확인** 단추입니다.  
  
3.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **NativeMathSDKSample** 프로젝트를 선택한 후 **추가**, **참조**합니다.  
  
4.  에 **공용 속성**, **프레임 워크 및 참조** 참조 형식의 목록에서 속성 페이지를 확장 하 고 **Windows**를 선택한 후 **확장** . 세부 정보 창에서 선택 된 **네이티브 수학 SDK** 확장을 선택한 후는 **새 참조 추가** 단추 합니다.  
  
5.  에 **참조 추가** 대화 상자는 **네이티브 수학 SDK** 확인란을 선택한 후는 **확인** 단추입니다.  
  
6.  NativeMathSDKSample에 대 한 프로젝트 속성을 표시 합니다.  
  
     참조를 추가 했을 때 NativeMathSDK.props에 정의 된 속성과 적용 된 합니다. 검사 하 여이 확인할 수 있습니다는 **VC + + 디렉터리** 는 프로젝트의 속성 **구성 속성**합니다.  
  
7.  **솔루션 탐색기**MainPage.xaml을 연 다음 다음 XAML을 사용 하 여 해당 콘텐츠를 대체 합니다.  
  
     [!code-xml[CreatingAnSDKUsingCppDemoApp#1](../extensibility/codesnippet/Xaml/walkthrough-creating-an-sdk-using-cpp_8.xaml)]  
  
8.  Mainpage.xaml.h이이 코드와 일치 하도록 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_9.h)]  
  
9. MainPage.xaml.cpp이이 코드와 일치 하도록 업데이트 합니다.  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_10.cpp)]  
  
10. 앱을 실행 하려면 F5 키를 선택 합니다.  
  
11. 앱에서 다음을 있는 두 숫자를 입력 하 여 작업을 선택한 다음 선택에서  **=**  단추입니다.  
  
     올바른 결과가 나타납니다.  
  
 이 연습에서는 만들고를 호출 하는 확장 SDK를 사용 하는 방법을 배웠습니다는 [!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] 라이브러리 및 비-[!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] 라이브러리입니다.  
  
## <a name="next-steps"></a>다음 단계  
  
## <a name="see-also"></a>참고 항목  
 [연습: C# 또는 Visual Basic을 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [소프트웨어 개발 키트 만들기](../extensibility/creating-a-software-development-kit.md)