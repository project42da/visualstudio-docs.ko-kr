---
title: "리소스에서 매니페스트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0234109b-5dcb-4d9d-acb9-a63f8bd5699c
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# 리소스에서 매니페스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

리소스 도구에서 매니페스트입니다 이미지 리소스 \(.png 또는.xaml 파일\)의 목록을 가져오고 해당 이미지를 Visual Studio 이미지 서비스와 함께 사용할 수 있는.imagemanifest 파일을 생성 하는 콘솔 응용 프로그램. 또한,이 도구를 사용 하는 기존.imagemanifest에 이미지를 추가할 수 있습니다. 이 도구는 Visual Studio 확장에는 이미지에 대 한 높은 DPI 및 테마 지원 추가 하는 데 유용 합니다. 생성 된.imagemanifest 파일에 포함 하 고 Visual Studio 확장 \(.vsix\)의 일부분으로 배포 해야 합니다.  
  
## 이 도구를 사용 하는 방법  
 **구문**  
  
 ManifestFromResources \/resources: \< Dir1 \>; \< Img1 \> \/assembly: \< AssemblyName \>\< 선택적 인수입니다. \>  
  
 **인수**  
  
||||  
|-|-|-|  
|**스위치 이름**|**참고**|**필수 또는 선택**|  
|\/resources|이미지 또는 디렉터리의 세미콜론으로 구분 된 목록입니다. 항상이 목록에는 매니페스트에 될 이미지의 전체 목록을 포함 되어 있어야 합니다. 하나만 목록의 일부 지정 된 경우에 포함 되지 않은 항목이 손실 됩니다.<br /><br /> 지정 된 리소스 파일의 이미지 스트립 경우 도구는로 분할 하 여 별도 이미지 각 subimage 매니페스트에 추가 하기 전에 합니다.<br /><br /> 이미지 파일은.png 파일이 있으면이 도구는 이미지에 대 한 올바른 특성에 채울 수 있도록 이름을 다음과 같이 형식 것이 좋습니다: \< 이름 \>. \< 너비 \>. \< 높이 \>.png입니다.|필수|  
|\/assembly|\(위치를 기준으로 매니페스트의 런타임\) 리소스를 호스팅하는 네이티브 어셈블리의 런타임 경로나 \(확장명 제외\), 관리 되는 어셈블리의 이름입니다.|필수|  
|\/manifest|생성 된.imagemanifest 파일에 부여할 이름입니다. 이 파일을 만들려면 다른 위치에는 절대 또는 상대 경로 포함할 수도 있습니다. 기본 이름은 어셈블리 이름과 일치 합니다.<br /><br /> 기본값: \< 현재 디렉터리 \> \\ \< 어셈블리 \>.imagemanifest|선택적|  
|\/guidName|모든 생성 된 매니페스트에서 이미지에 대 한 GUID 기호에 부여할 이름입니다.<br /><br /> 기본값: AssetsGuid|선택적|  
|\/rootPath|관리 되는 리소스 Uri를 만들기 전에 제거 되어야 하는 루트 경로입니다. \(이 플래그는 여기서 도구 상대 URI 경로 가져옵니다 잘못, 리소스를 로드할 수 없게 되어 발생 하는 경우에 도움이 되도록 합니다.\)<br /><br /> 기본값: \< 현재 디렉터리 \>|선택적|  
|\/recursive|이 플래그를 설정에 재귀적으로 도구에 지시 \/resources 인수에 모든 디렉터리를 검색 합니다. 이 플래그를 생략 하면 디렉터리의 최상위 level만 검색 됩니다.|선택적|  
|\/isNative|어셈블리 인수가 네이티브 어셈블리에 대 한 경로 하는 경우이 플래그를 설정 합니다. 어셈블리 인수가 관리 되는 어셈블리의 이름을 하는 경우이 플래그를 생략 합니다. \(이 플래그에 대 한 자세한 내용은 참고 섹션 참조\).|선택적|  
|\/newGuids|이 플래그를 설정 합니다. 기존 매니페스트를 병합 하는 대신 이미지의 GUID 기호에 대 한 새 값을 만드는 도구를 알립니다.|선택적|  
|\/newIds|이 플래그를 설정 합니다. 기존 매니페스트의 값을 병합 하는 대신 모든 이미지에 대 한 새 ID 기호 값을 만드는 도구를 알립니다.|선택적|  
|\/noLogo|인쇄에서 제품 및 저작권 정보를 중지이 플래그를 설정 합니다.|선택적|  
|\/?|도움말 정보를 출력 합니다.|선택적|  
|\/help|도움말 정보를 출력 합니다.|선택적|  
  
 **예제**  
  
-   ManifestFromResources \/resources:D:\\Images \/assembly:My.Assembly.Name \/isNative  
  
-   ManifestFromResources \/resources:D:\\Images\\Image1.png;D:\\Images\\Image1.xaml \/assembly:My.Assembly.Name \/manifest:MyImageManifest.imagemanifest  
  
-   ManifestFromResources \/resources:D:\\Images\\Image1.png;D:\\Images\\Image1.xaml \/assembly:My.Assembly.Name \/guidName:MyImages \/newGuids \/newIds  
  
## 참고  
  
-   이 도구는만.png 및.xaml 파일을 지원합니다. 다른 이미지 또는 파일 형식 무시 됩니다. 리소스를 구문 분석 하는 동안 발생 하는 모든 지원 되지 않는 형식에 대해 경고가 생성 됩니다. 이미지 도구 완료 되 면이 발견 되는 경우를 지원 하지 않습니다 리소스, 구문 분석 오류가 생성 됩니다  
  
-   .Png 이미지에 대 한 제안 된 형식에 따라 도구는 크기\/차원 값을 설정는.png 형식 지정 된 크기를 이미지의 실제 크기에서 서로 다른 경우에 합니다.  
  
-   .Png 이미지에 대 한 너비\/높이 서식을 생략할 수 있습니다 하지만 도구는 이미지의 실제 너비\/높이 읽고 이미지의 크기\/차원 값에 대 한 역할을 사용 합니다.  
  
-   도구를 독립 실행형 이미지를 이미지 스트립을 분할 하 고 기존 매니페스트를 추가 하려고 하기 때문에 여러 번에 대 한 동일한.imagemanifest 동일한 이미지 스트립에서이 도구를 실행 중복 매니페스트 항목이 발생 합니다.  
  
-   도구에서 생성 된 매니페스트에 대 한 병합 \(\/newGuids 또는 \/newIds 생략\)만 수행 해야 합니다. 사용자 지정 또는 다른 수단을 통해 생성 된 매니페스트를 올바르게 병합 될 수 있습니다.  
  
-   네이티브 어셈블리에 대해 생성 된 매니페스트 리소스 네이티브 어셈블리의.rc 파일에서 Id와 일치 하는 ID 기호는 생성 후을 수동으로 편집 수 해야 합니다.  
  
## 샘플 출력  
 **간단한 이미지 매니페스트**  
  
 이미지 매니페스트가.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?> <!-- This file was generated by the ManifestFromResources tool.--> <!-- Version: 14.0.15197 --> <ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014"> <Symbols> <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/Images" /> <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" /> <ID Name="MyImage" Value="0" /> </Symbols> <Images> <Image Guid="$(AssetsGuid)" ID="$(MyImage)"> <Source Uri="$(Resources)/Xaml/MyImage.xaml" /> <Source Uri="$(Resources)/Png/MyImage.16.16.png"> <Size Value="16" /> </Source> </Image> </Images> <ImageLists /> </ImageManifest>  
```  
  
 **이미지 스트립에 대 한 이미지 매니페스트**  
  
 이미지 스트립에 대 한 이미지 매니페스트가.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?> <!-- This file was generated by the ManifestFromResources tool.--> <!-- Version: 14.0.15197 --> <ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014"> <Symbols> <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/ImageStrip" /> <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" /> <ID Name="MyImageStrip_0" Value="1" /> <ID Name="MyImageStrip_1" Value="2" /> <ID Name="MyImageStrip" Value="3" /> </Symbols> <Images> <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)"> <Source Uri="$(Resources)/MyImageStrip_0.png"> <Size Value="16" /> </Source> </Image> <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)"> <Source Uri="$(Resources)/MyImageStrip_1.png"> <Size Value="16" /> </Source> </Image> </Images> <ImageLists> <ImageList Guid="$(AssetsGuid)" ID="$(MyImageStrip)"> <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)" /> <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)" /> </ImageList> </ImageLists> </ImageManifest>  
```  
  
 **네이티브 어셈블리 이미지 리소스에 대 한 이미지 매니페스트**  
  
 네이티브 이미지에 대 한 이미지 매니페스트가.xml 파일에 유사한 됩니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?> <!-- This file was generated by the ManifestFromResources tool.--> <!-- Version: 14.0.15198 --> <ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014"> <Symbols> <String Name="Resources" Value="..\Assembly\Folder\My.Assembly.Name" /> <Guid Name="AssetsGuid" Value="{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}" /> <ID Name="MyImage1" Value="0" /> <ID Name="MyImage2" Value="1" /> </Symbols> <Images> <Image Guid="$(AssetsGuid)" ID="$(MyImage1)"> <Source Uri="$(Resources)"> <Size Value="16" /> <NativeResource ID="$(MyImage1)" Type="PNG" /> </Source> </Image> <Image Guid="$(AssetsGuid)" ID="$(MyImage2)"> <Source Uri="$(Resources)"> <Size Value="16" /> <NativeResource ID="$(MyImage2)" Type="PNG" /> </Source> </Image> </Images> <ImageLists /> </ImageManifest>  
```