---
title: "샘플 Excel 확장: ExtensionPackage 클래스 | Microsoft 문서"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2d4c7b5c3aefbc59b8e8931376f0bcf14951c9bc
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-extension-extensionpackage-class"></a>샘플 Excel 확장: ExtensionPackage 클래스
이 클래스는 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> 클래스를 확장하며 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 워크시트를 테스트하는 코딩된 UI 테스트의 진입점을 제공합니다.

## <a name="assembly-attribute"></a>Assembly 특성
 파일은 어셈블리를 UI 테스트 확장으로 식별하는 assembly 특성으로 시작됩니다.

```
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(
    "ExcelExtensionPackage",
    typeof(
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]
```

 이 특성은 기본 클래스 이름, 패키지 클래스 이름, 그리고 사용자 지정 확장 패키지 클래스의 정규화된 클래스 이름을 선언합니다.

## <a name="simple-properties"></a>단순 속성
 이 클래스에는 코딩된 UI 테스트 프레임워크가 확장과 어셈블리를 식별하고 설명하는 데 사용하는 값을 제공하는 속성이 있습니다. 자세한 내용은 코드 주석을 참조하세요.

## <a name="getservice-method"></a>GetService 메서드
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> 메서드는 코딩된 UI 테스트 프레임워크가 각 개체의 기본 클래스로 식별되는 기술 관리자, 속성 공급자 및 작업 필터에 액세스하는 데 사용하는 단일 진입점입니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [Microsoft Excel을 지원하도록 코딩된 UI 테스트 및 작업 기록 확장](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
