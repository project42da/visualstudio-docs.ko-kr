---
title: "Visual Studio 명령 테이블 (. Vsct) 파일 | Microsoft Docs"
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
  - "VSCT 파일, 개요"
  - "Visual Studio 명령 테이블 구성 파일 (VSCT), 개요"
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: 22
caps.handback.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
---
# Visual Studio 명령 테이블 (. Vsct) 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

명령 테이블 구성 파일은 VSPackage를 포함 하는 명령 집합을 설명 하는 텍스트 파일입니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 테이블 \(VSCT\) 컴파일러 이진 명령 테이블 \(.cto\) 출력 파일을 XML 기반 구성 파일 \(.vsct 파일\)를 컴파일합니다. 결과.cto 파일.ctc 구성 파일을 컴파일하려면 명령 테이블 \(CTC\) 컴파일러를 사용 하 여 만들어진 것과 동일 합니다. 그러나 XML 기반.vsct 파일에는 XML 편집기 및 XML IntelliSense와 같은 몇 가지 이점이 있습니다.  
  
 구문 및 의미 체계의.vsct 파일에 대 한 자세한 내용은 참조 하세요. [XML 명령 테이블 디자인 \(합니다. Vsct\) 파일](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## 단원 내용  
 [XML 명령 테이블 디자인 \(합니다. Vsct\) 파일](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 .Vsct 파일을 디자인 하는 방법에 설명 합니다.  
  
 [방법: 만들기는 합니다. Vsct 파일](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 .Vsct 파일을 만들기 위한 메서드를 비교 합니다. 수동으로 새.vsct 파일을 만드는 프로세스를 설명 합니다.  
  
## 관련 단원  
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)  
 명령 테이블 XML 구성 파일의 각 섹션에 대 한 세부 정보를 제공합니다.  
  
 [Command Table Configuration \(.Ctc\) Files](http://msdn.microsoft.com/ko-kr/3413dda1-f372-4669-bcf0-c64d3463842c)  
 사용 되지 않는.ctc 파일 형식에 대 한 개요를 표시합니다.  
  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 명령 테이블 형식 지정에 설명 합니다.  
  
 [Vspackage의 리소스](../../extensibility/internals/resources-in-vspackages.md)  
 관리 되는 VSPackages에 스레드와 관리 되지 않는 리소스를 사용 하는 방법에 설명 합니다.  
  
 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)  
 메뉴, 도구 모음 및 명령 콤보 상자를 포함 하는 UI를 만드는 방법에 설명 합니다.