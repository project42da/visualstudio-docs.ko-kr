---
title: 배포 된 ASP.NET 응용 프로그램 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET Web applications
- Web services, debugging
- XML, debugging Web services
- debugging Web services
- ASP.NET, debugging Web applications
- XML Web services, debugging
ms.assetid: b938a91b-be96-416f-83bc-4177e7f3929a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: b8c7c9ea2f280eaf60f4592f149ed2989d862b9b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-deployed-aspnet-applications"></a>배포 된 ASP.NET 응용 프로그램 디버깅
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 배포된 응용 프로그램을 디버깅하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스에 연결하고 디버거에서 해당 응용 프로그램에 대한 기호에 액세스할 수 있는지 확인해야 합니다. 또한 해당 응용 프로그램의 소스 파일도 찾아서 열어야 합니다. 자세한 내용은 참조 [지정 기호 (.pdb) 및 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md), [하는 방법: ASP.NET 프로세스의 이름 찾기](../debugger/how-to-find-the-name-of-the-aspnet-process.md), 및 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)합니다.  

> [!WARNING]
> 에 연결 하는 경우는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스의 디버깅 및 적중 된 중단점의에서 모든 관리 코드가 작업자 프로세스가 중단 합니다. 서버의 모든 사용자에 대해 작업이 중지될 수 있습니다. 프로덕션 서버에서 디버깅하려면 프로덕션 작업에 미칠 수 있는 모든 영향을 고려해야 합니다. 
  
[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스에 연결하는 프로세스는 다른 모든 원격 프로세스에 연결하는 방법과 동일합니다. 연결 된 경우, 올바른 프로젝트를 열고 하지 않은 경우, 응용 프로그램이 중단 될 때 대화 상자가 나타납니다. 이 대화 상자에는 응용 프로그램의 소스 파일 위치를 지정하라는 메시지가 표시됩니다. 대화 상자에서 지정한 파일 이름은 웹 서버에 있는 디버그 기호에 지정한 파일 이름과 일치해야 합니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다. 참조를 IIS에 원격 디버깅을 설정 하려면 [원격 IIS 컴퓨터에 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)합니다.
 
> [!NOTE]
>  대부분의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에서는 비즈니스 논리나 다른 유용한 코드가 포함된 DLL을 참조합니다. 앱을 배포할 때 참조 되는 이러한 DLL은 로컬 컴퓨터에서 웹 응용 프로그램의 가상 디렉터리의 \bin 폴더에 복사 합니다. 디버깅하는 경우 웹 응용 프로그램이 로컬 컴퓨터에 있는 DLL 복사본이 아니라 가상 디렉터리에 있는 DLL 복사본을 참조한다는 점에 주의합니다. 
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 응용 프로그램 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [방법: ASP.NET 응용 프로그램에 디버깅 사용](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [방법: ASP.NET 프로세스의 이름 찾기](../debugger/how-to-find-the-name-of-the-aspnet-process.md)   
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)