---
title: "라이선스 요소 (VSIX 언어 팩 스키마) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 57dac3b7-0cdd-405c-9af5-30ed9ca45e53
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# 라이선스 요소 (VSIX 언어 팩 스키마)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

선택적 요소. 지역화 된 버전의 확장에 대 한 라이선스 파일의 경로입니다.  
  
## 구문  
  
```  
<License>FilePath\license.txt</License>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|없음||  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|없음||  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[VSIX 언어 요소](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|필수 요소. VSIX 언어 팩에 대 한 루트 요소를 제공 합니다.|  
  
## 텍스트 값  
 표시할 지역화 된 라이센스 파일의 상대 경로입니다.  
  
## 설명  
 하는 경우는 `License` 요소가 정의 된 다음 지정된 된 라이선스 파일의 텍스트는 설치 하는 동안 표시 되 고 사용자를 계속 사용에 동의 해야 합니다.  
  
## 요소 정보  
  
|||  
|-|-|  
|네임스페이스|http:\/\/schemas.microsoft.com\/developer\/vsx\-schema\-lp\/2010|  
|스키마 이름|VSIX 언어 팩 스키마|  
|유효성 검사 파일|VSIXLanguagePackSchema.xsd|  
|비워 둘 수 있습니다.|적용할 수 없음|  
  
## 참고 항목  
 [VSX 언어 팩 스키마 참조](../extensibility/vsx-language-pack-schema-reference.md)   
 [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)   
 [VSIX 확장 1.0 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)