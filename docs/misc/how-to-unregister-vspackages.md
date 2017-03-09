---
title: "방법: VSPackage 등록 취소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "샘플 응용 프로그램[Visual Studio SDK], 제거"
  - "설치, VSPackage"
ms.assetid: b51522f0-c033-4d93-b928-2171a953032b
caps.latest.revision: 14
caps.handback.revision: 14
manager: "douge"
---
# 방법: VSPackage 등록 취소
기본적으로 VSPackage는 빌드될 때 실험적 레지스트리 하이브에 등록됩니다. 실험적 하이브는 VSPackage로 실험한 후 유지하지 않으려는 VSPackage로 채워질 수 있습니다.  
  
 실험적 하이브에 등록된 모든 패키지를 삭제하려면 \/Reset 옵션과 함께 CreateExpInstance 도구를 사용하여 하이브를 초기화합니다. 자세한 내용은 [실험적 인스턴스](../extensibility/the-experimental-instance.md)을 참조하세요.  
  
## 개별 VSPackage 등록 취소  
  
#### 관리되지 않는 VSPackage의 등록을 취소하려면  
  
1.  **시작** 메뉴에서 **실행**을 클릭하고 `regsvr32 /u` *pathToVSPackage.dll*을 입력한 다음 확인을 클릭합니다.  
  
 관리되지 않는 VSPackage에는 자동 등록 코드가 없으므로 regsvr32 유틸리티를 사용하여 등록하거나 등록을 취소할 수 있습니다.  
  
#### 관리되는 VSPackage 등록을 취소하려면  
  
1.  **시작** 메뉴에서 **실행**을 클릭하고 *Visual Studio SDK 설치 경로*`\EnvSDK\tools\bin\x86\regpkg /unregister` *pathToVSPackage.dll*을 입력한 다음 확인을 클릭합니다.  
  
 RegPkg 도구는 관리되는 VSPackage에 포함될 수 있는 등록 특성을 읽습니다.**\/unregister** 스위치는 RegPkg가 레지스트리에서 정보를 제거하도록 합니다.  
  
## 참고 항목  
 [Visual Studio Integration Samples](http://msdn.microsoft.com/ko-kr/b5dbf078-3af2-4fed-a1ea-171e4ee73a43)