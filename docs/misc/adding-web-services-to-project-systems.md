---
title: "프로젝트 시스템에 웹 서비스 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 시스템, 웹 서비스 추가"
  - "웹 서비스, VSPackage 프로젝트 시스템에 추가"
ms.assetid: 8efa078b-68b2-45a2-9be2-44f807bc0d7f
caps.latest.revision: 8
caps.handback.revision: 8
manager: "douge"
---
# 프로젝트 시스템에 웹 서비스 추가
XML 웹 서비스는 일반적으로 SOAP \(단순 개체 액세스 프로토콜\) 프로토콜을 사용 하 여 프로젝트 시스템을 프로그래밍 방식으로 정보를 반환 하는 URL 주소 지정 가능 리소스입니다.  사용 하 여 VSPackage 프로젝트 시스템에 웹 서비스 통합의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg2> 인터페이스입니다.  
  
### 프로젝트 시스템에는 웹 서비스를 추가 하려면  
  
1.  호출 `QueryService` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg2> 인터페이스를 통해 <xref:Microsoft.VisualStudio.Shell.Interop.SVsAddWebReferenceDlg> 서비스 합니다.  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2.AddWebReferenceDlg%2A> 메서드를 호출합니다.  에 전달 하는 경우 `pDiscoverySession` 매개 변수로 `NULL`, 검색 세션 생성 됩니다 및 이후에 사용할 수 있도록 세션 캐시 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2> 인터페이스.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2.AddWebReferenceDlg%2A>방법에 대 한 포인터를 반환 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult2>.  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult.AddWebReference%2A> 메서드를 호출합니다.  자동화 개체에 전달 하는 웹 서비스 참조 폴더의 `pUnkWebReferenceFolder` 매개 변수.  Visual Studio 환경 하에 웹 서비스가 표시 되는지 확인 합니다.  웹 서비스가 있는 경우 환경을 다운로드 하는 웹 서비스 폴더와 폴더의 자식 노드를 추가 파일 \(예:.wsdl 파일\)을 추가 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoveryResult>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IDiscoverySession>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDiscoveryService>