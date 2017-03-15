---
title: "설정 가져오기 및 내보내기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Tools.ImportandExportSettings"
helpviewer_keywords: 
  - "Tools.ImportandExportSettings"
  - "설정 가져오기 및 내보내기 명령"
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# 설정 가져오기 및 내보내기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설정을 가져오거나, 내보내거나, 다시 설정합니다.  
  
## 구문  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## 스위치  
 \/export:`filename`  
 선택적 요소.  현재 설정을 지정한 파일로 내보냅니다.  
  
 \/import:`filename`  
 선택적 요소.  지정한 파일에서 설정을 가져옵니다.  
  
 \/reset 또는 \/다시설정  
 선택적 요소.  현재 설정을 다시 설정합니다.  
  
## 설명  
 이 명령을 스위치 없이 실행하면 **설정 가져오기 및 내보내기** 마법사가 열립니다.  자세한 내용은 [How to: Share Settings Between Computers or Visual Studio Versions](http://msdn.microsoft.com/ko-kr/1131fb10-35c1-42da-9cd8-91aa3235b882)를 참조하십시오.  
  
## 예제  
 다음 명령은 현재 설정을 `MyFile.vssettings` 파일로 내보냅니다.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## 참고 항목  
 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)