---
title: "식 계산기를 등록 하는 중 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 식 계산"
  - "등록 하는 식 계산기"
ms.assetid: 236be234-e05f-4ad8-9200-24ce51768ecf
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 식 계산기를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 \(EE\) 자체는 Windows COM 환경 및 Visual Studio와 클래스 팩터리로 등록 해야 합니다. EE는 디버그 엔진 \(DE\) 주소 공간 또는 따라 엔터티 EE를 인스턴스화하는 Visual Studio 주소 공간에 주입 될 수 있도록 DLL로 구현 됩니다.  
  
## 관리 코드 식 계산기  
 EE 클래스 라이브러리에는 VSIP 프로그램에 대 한 호출에 의해 시작 일반적으로 COM 환경에 등록 되는 DLL로 구현 되는 관리 코드 **regpkg.exe**합니다. 실제 COM 환경에 대 한 레지스트리 키를 쓰는 과정은 자동으로 처리 됩니다.  
  
 기본 클래스의 메서드를 표시는 <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>, com DLL이 등록 될 때 호출 되는 메서드 임을 나타내는 이 등록 메서드를 종종 라고 `RegisterClass`, Visual Studio와 함께 DLL을 등록 하는 작업을 수행 합니다. 해당 `UnregisterClass` \(으로 표시는 <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>\), 수행한 `RegisterClass` DLL을 제거 하면 됩니다.  
  
 동일한 레지스트리 항목의 경우 관리 되지 않는 코드에서 작성 하는 EE와 이루어집니다. 유일한 차이점은는 도우미 함수는 같은 `SetEEMetric` 에서 작업을 수행 하도록 합니다. 이 등록\/등록 취소 프로세스의 예는 다음과 같습니다.  
  
### 예제  
 이 함수에는 관리 코드 EE 등록 하 고 Visual Studio와 함께 자체 등록을 취소 하는 방법을 보여 줍니다.  
  
```c#  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        #region Register and unregister.  
        private static Guid guidMycLang = new Guid("462D4A3E-B257-4AEE-97CD-5918C7531757");  
        private static string languageName = "MyC";  
        private static string eeName = "MyC Expression Evaluator";  
  
        private static Guid guidMicrosoftVendor = new Guid("994B45C4-E6E9-11D2-903F-00C04FA302A1");  
        private static Guid guidCOMPlusOnlyEng = new Guid("449EC4CC-30D2-4032-9256-EE18EB41B62B");  
        private static Guid guidCOMPlusNativeEng = new Guid("92EF0900-2251-11D2-B72E-0000F87572EF");  
  
        /// <summary>  
        /// Register the expression evaluator.  
        /// Set "project properties/configuration properties/build/register for COM interop" to true.  
        /// </summary>  
         [ComRegisterFunctionAttribute]  
        public static void RegisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator";  
  
            RegistryKey rk = Registry.LocalMachine.CreateSubKey(s);  
            if (rk == null)  return;  
  
            rk = rk.CreateSubKey(guidMycLang.ToString("B"));  
            rk = rk.CreateSubKey(guidMicrosoftVendor.ToString("B"));  
            rk.SetValue("CLSID", t.GUID.ToString("B"));  
            rk.SetValue("Language", languageName);  
            rk.SetValue("Name", eeName);  
  
            rk = rk.CreateSubKey("Engine");  
            rk.SetValue("0", guidCOMPlusOnlyEng.ToString("B"));  
            rk.SetValue("1", guidCOMPlusNativeEng.ToString("B"));  
        }  
        /// <summary>  
        /// Unregister the expression evaluator.  
        /// </summary>  
         [ComUnregisterFunctionAttribute]  
        public static void UnregisterClass(Type t)  
        {  
            // Get Visual Studio version (set by regpkg.exe)  
            string hive = Environment.GetEnvironmentVariable("EnvSdk_RegKey");  
            string s = @"SOFTWARE\Microsoft\VisualStudio\"  
                        + hive  
                        + @"\AD7Metrics\ExpressionEvaluator\"  
                        + guidMycLang.ToString("B");  
            RegistryKey key = Registry.LocalMachine.OpenSubKey(s);  
            if (key != null)  
            {  
                key.Close();  
                Registry.LocalMachine.DeleteSubKeyTree(s);  
            }  
        }  
    }  
}  
```  
  
## 관리 되지 않는 코드 식 계산기  
 EE DLL를 구현 하는 `DllRegisterServer` 함수 COM 환경 뿐만 아니라 Visual Studio에 등록 되도록 합니다.  
  
> [!NOTE]
>  MyCEE 코드 샘플 레지스트리 코드 VSIP 설치 EnVSDK\\MyCPkgs\\MyCEE 아래에 있는 파일 dllentry.cpp에서 찾을 수 있습니다.  
  
### DLL 서버 프로세스  
 DLL 서버 EE 등록 하는 경우:  
  
1.  해당 클래스 팩터리를 등록 `CLSID` 일반 COM 규칙에 따라 합니다.  
  
2.  도우미 함수를 호출 `SetEEMetric` EE 메트릭을 다음 표에 표시 된 Visual Studio와 함께 등록 합니다. 함수 `SetEEMetric` 되며 아래에 지정 된 메트릭 dbgmetric.lib 라이브러리의 일부가 됩니다. 자세한 내용은 [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)를 참조하세요.  
  
    |메트릭|설명|  
    |---------|--------|  
    |`metricCLSID`|`CLSID` EE 클래스 팩터리|  
    |`metricName`|표시할 수 있는 문자열로 EE의 이름|  
    |`metricLanguage`|평가 하도록 디자인 된 EE 되는 언어의 이름|  
    |`metricEngine`|`GUID`가이 EE를 사용 하는 디버그 엔진 \(DE\)|  
  
    > [!NOTE]
    >  `metricLanguage` `GUID` 이름에서 언어를 식별 하는 `guidLang` 인수를 `SetEEMetric` 언어를 선택 하는 합니다. 컴파일러에서 디버그 정보 파일을 생성할 때 적절 한 작성 해야 `guidLang` 는 DE 사용 하 여 어떤 EE 알 수 있도록 합니다. 일반적으로 DE이이 언어에 대 한 기호 공급자를 요청 `GUID`, 디버그 정보 파일에 저장 되어 있습니다.  
  
3.  HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\ 아래에 키를 만들어 Visual Studio와 함께 등록*X.Y*, 여기서 *X.Y* 를 등록 하려면 Visual Studio의 버전입니다.  
  
### 예제  
 이 함수는 관리 되지 않는 코드 \(c \+ \+\) EE 등록 하 고 Visual Studio와 함께 자체 등록을 취소 하는 방법을 보여 줍니다.  
  
```cpp#  
/*---------------------------------------------------------  
  Registration  
-----------------------------------------------------------*/  
#ifndef LREGKEY_VISUALSTUDIOROOT  
    #define LREGKEY_VISUALSTUDIOROOT L"Software\\Microsoft\\VisualStudio\\8.0"  
#endif  
  
static HRESULT RegisterMetric( bool registerIt )  
{  
    // check where we should register  
    const ULONG cchBuffer = _MAX_PATH;  
    WCHAR wszRegistrationRoot[cchBuffer];  
    DWORD cchFreeBuffer = cchBuffer - 1;  
    wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT_NOVERSION);  
    wcscat(wszRegistrationRoot, L"\\");  
  
    // this is Environment SDK specific  
    // we check for  EnvSdk_RegKey environment variable to  
    // determine where to register  
    DWORD cchDefRegRoot = lstrlenW(LREGKEY_VISUALSTUDIOROOT_NOVERSION) + 1;  
    cchFreeBuffer = cchFreeBuffer - cchDefRegRoot;  
    DWORD cchEnvVarRead = GetEnvironmentVariableW(  
        /* LPCTSTR */ L"EnvSdk_RegKey", // environment variable name  
        /* LPTSTR  */ &wszRegistrationRoot[cchDefRegRoot],// buffer for variable value  
        /* DWORD   */ cchFreeBuffer);// size of buffer  
    if (cchEnvVarRead >= cchFreeBuffer)  
        return E_UNEXPECTED;  
    // If the environment variable does not exist then we must use   
    // LREGKEY_VISUALSTUDIOROOT which has the version number.  
    if (0 == cchEnvVarRead)  
        wcscpy(wszRegistrationRoot, LREGKEY_VISUALSTUDIOROOT);  
  
    if (registerIt)  
    {  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricCLSID,  
                    CLSID_MycEE,  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricName,  
                    GetString(IDS_INFO_MYCDESCRIPTION),  
                    wszRegistrationRoot );  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricLanguage, L"MyC",  
                    wszRegistrationRoot);  
  
        GUID engineGuids[2];  
        engineGuids[0] = guidCOMPlusOnlyEng;  
        engineGuids[1] = guidCOMPlusNativeEng;  
        SetEEMetric(guidMycLang,  
                    guidMicrosoftVendor,  
                    metricEngine,  
                    engineGuids,  
                    2,  
                    wszRegistrationRoot);  
    }  
    else  
    {  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricCLSID,  
                        wszRegistrationRoot);  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricName,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricLanguage,  
                        wszRegistrationRoot );  
        RemoveEEMetric( guidMycLang,  
                        guidMicrosoftVendor,  
                        metricEngine,  
                        wszRegistrationRoot );  
    }  
  
    return S_OK;  
}  
```  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)