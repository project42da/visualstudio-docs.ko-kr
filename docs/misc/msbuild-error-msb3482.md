---
title: "MSBuild 오류 MSB3482 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.SignFile.SignToolError"
helpviewer_keywords: 
  - "MSB3482"
ms.assetid: fd09371f-2658-4534-affa-edb485575f1a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3482
**MSB3482: 서명하는 동안 오류가 발생했습니다. '\<error\>'**  
  
 ClickOnce 배포를 사용하여 게시하거나 매니페스트에 서명하는 데 SignTool을 사용 중인 경우 SignTool에서 오류를 생성할 수 있습니다. 일반적인 문제는 다음과 같습니다.  
  
 **서명하는 동안 오류가 발생했습니다. '값이 null일 수 없습니다. 매개 변수 이름: strongNameKey'**  
  
 이 오류는 ClickOnce 배포 중 오류 목록에 나타날 수 있습니다. 이 문제는 잘못된 서명 키를 선택하여 발생합니다. 일반적으로 RSA 암호화가 아닌 키를 사용하려고 합니다. SignTool은 RSA 키 암호화만 지원합니다.  
  
 이 오류를 해결하려면 코드 서명을 사용하도록 설정한 RSA 암호화 키를 얻습니다.  
  
 **서명하는 동안 오류가 발생했습니다. ‘인증서 체인을 신뢰할 수 있는 루트 인증 기관에 빌드할 수 없습니다.’**  
  
 이 오류는 ClickOnce 배포 중 오류 목록에 나타날 수 있습니다. 문제는 인증서에 사용자의 컴퓨터에서 신뢰할 수 없는 체인이나 루트 인증 기관이 포함된다는 것입니다. 이 문제는 일반적으로 인증서\/키를 컴퓨터 간에 이동할 때 발생합니다.  
  
 이 오류를 해결하려면 인증서를 만든 CA\(인증 기관\)의 "루트 인증서"를 설치합니다. 일반적으로 CA 공급업체의 웹 사이트로 이동하여 필요에 따라 다시 다운로드할 수 있습니다.  
  
 **서명하는 동안 오류가 발생했습니다. '...\\setup.exe에 서명하지 못했습니다. SignTool 오류: ISignCode::Sign 반환된 오류: 0x80880253 서명자의 인증서가 서명에 유효하지 않습니다.'**  
  
 이 오류는 ClickOnce 배포 중 오류 목록에 나타날 수 있습니다.  
  
 이 문제는 대부분 인증서가 유효한 날짜 내에 있지 않아서 발생하는데, 예를 들어 인증서가 만료된 경우입니다.  
  
 이 오류를 해결하려면 유효한 날짜로 업데이트된 인증서를 얻습니다.  
  
 인증서를 업데이트하는 방법에 대한 자세한 내용은 Microsoft 기술 자료 문서\([http:\/\/support.microsoft.com](http://support.microsoft.com/kb/925521)\)에서 925521 문서, "설치에 서명하는 데 사용된 인증서가 만료된 후에 Visual Studio 2005 ClickOnce 응용 프로그램을 업데이트하려고 하는 경우 오류 메시지를 받음"\(영문\)을 참조하세요.  
  
 **키 집합이 없습니다.**  
  
 .pfx 파일과 인증서가 일치하지 않을 수 있습니다. 인증서 삭제와 다시 설치 및\/또는 .pfx 파일 다시 만들기를 시도합니다.  
  
 **지정된 상태에서 사용하기에 유효한 키가 아닙니다.**  
  
 참조: http:\/\/blogs.msdn.com\/b\/smondal\/archive\/2012\/05\/08\/an\-error\-occurred\-while\-signing\-key\-not\-valid\-for\-use\-in\-specified\-state.aspx  
  
 **매개 변수가 잘못되었습니다.**  
  
 빌드가 인증서를 가져오지 않은 다른 서비스 또는 사용자 계정에서 실행되고 있나요? 개인 키 보호가 필요한 임의 로컬 보안 정책 설정을 해제해 봅니다.  그런 다음 빌드 사용자 계정에 대한 인증서를 삭제하고 다시 가져옵니다.  
  
 **요청한 작업을 완료할 수 없습니다.  컴퓨터는 위임을 위해 신뢰할 수 있어야 하며 현재 사용자 계정은 위임을 허용하도록 구성해야 합니다.**  
  
 [이 MSDN 블로그 게시](http://technet.microsoft.com/en-us/library/cc782684\(v=ws.10\).aspx)를 참조하세요.  
  
## 참고 항목  
 [코드 서명 소개](https://msdn.microsoft.com/en-us/library/ms537361\(v=vs.85\).aspx)   
 [SignTool.exe\(서명 도구\)](../Topic/SignTool.exe%20\(Sign%20Tool\).md)   
 [프로젝트 디자이너, 서명 페이지](../ide/reference/signing-page-project-designer.md)   
 [방법: 어셈블리 서명\(Visual Studio\)](http://msdn.microsoft.com/ko-kr/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [방법: 강력한 이름으로 어셈블리 서명](../Topic/How%20to:%20Sign%20an%20Assembly%20with%20a%20Strong%20Name.md)   
 [강력한 이름의 어셈블리](../Topic/Strong-Named%20Assemblies.md)   
 [관리되는 응용 프로그램에 대한 강력한 이름 서명](http://msdn.microsoft.com/ko-kr/5fef3490-c519-4363-94fd-8b1ad260dab5)   
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)