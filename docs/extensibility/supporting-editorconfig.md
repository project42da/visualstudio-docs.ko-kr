---
title: Visual Studio에서 EditorConfig를 지원 하기 위해 언어 서비스 확장 | Microsoft Docs
ms.custom: ''
ms.date: 11/22/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2aa80903b3e5ea2723ec576fa463161b8d003c93
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-editorconfig-for-your-language-service"></a>EditorConfig 언어 서비스에 대 한 지원

[EditorConfig](http://editorconfig.org/) 파일을 사용 하는 프로젝트 수준이에서 들여쓰기 크기와 같은 일반 텍스트 편집기 옵션을 설명할 수 있습니다. EditorConfig 파일에 대 한 Visual Studio의 지원에 대 한 자세한 참조 [EditorConfig를 사용 하 여 휴대용 편집기 설정을 만들](../ide/create-portable-custom-editor-options.md)합니다.

대부분의 경우 Visual Studio 언어 서비스를 구현할 때 EditorConfig 유니버설 속성을 지원하기 위해 추가 작업이 필요하지 않습니다. 사용자가 파일을 열면 코어 편집기에서 .editorconfig 파일을 자동으로 검색하여 읽은 다음 적절한 텍스트 버퍼와 보기 옵션을 설정합니다. 그러나 탭 및 공간과 같은 편집 작업에 대 한 일부 언어 서비스의 전역 설정을 사용 하 여 보다는 적절 한 상황에 맞는 텍스트 보기 옵션 사용 하도록 선택. 이러한 경우 EditorConfig 파일을 지원하도록 언어 서비스를 업데이트해야 합니다.

다음은 전역 대체 하 여 EditorConfig 파일을 지원 하기 위해 언어 서비스를 업데이트 하는 데 필요한 변경 내용을 _언어별_ 옵션과 함께 _상황별_ 옵션:

## <a name="indent-style"></a>들여쓰기 스타일

언어 관련 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>들여쓰기 크기

언어 관련 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>탭 크기

언어 관련 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>참고자료

[EditorConfig를 사용 하 여 휴대용 편집기 설정 만들기](../ide/create-portable-custom-editor-options.md)  
[편집기 및 언어 서비스를 확장합니다.](../extensibility/extending-the-editor-and-language-services.md)