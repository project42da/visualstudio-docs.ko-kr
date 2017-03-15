---
title: "방법: 백그라운드 스레드에서 서비스 가져오기(C++) | Microsoft Docs"
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
  - "다중 스레딩, 서비스"
ms.assetid: 97a56709-66d4-431a-ae63-392ee5898511
caps.latest.revision: 8
caps.handback.revision: 8
manager: "douge"
---
# 방법: 백그라운드 스레드에서 서비스 가져오기(C++)
방법으로 서비스를 얻을 수 없습니다 `IServiceProvider.QueryService` 백그라운드 스레드가 있습니다.  사용 하는 경우 `QueryService` 주 스레드에서 서비스를 준비 하 고 서비스는 백그라운드 스레드에서 사용 하려고 하는 실패할 수도 있습니다.  
  
 서비스는 백그라운드 스레드를 사용 `CoMarshalInterThreadInterfaceInStream` 에 있는 `IVsPackage.SetSite` 메서드를 서비스 공급자에 주 스레드에서 스트림으로 마샬링합니다.  다음 서비스 공급자는 백그라운드 스레드에서 역마샬링 하 고 서비스를 사용 하 여 있습니다.  역마샬링을 한 번만, 따라서 반환 되는 인터페이스를 캐시할 수 있습니다.  
  
> [!NOTE]
>  관리 코드는 자동으로 백그라운드 스레드에서 서비스를 얻는 특별 한 코드가 필요 하지 않습니다 있도록 스레드 간에 인터페이스를 마샬링합니다.  
  
## 예제  
 서비스 공급자가 주 스레드에 마샬링합니다 하 고 제공 하는 다음 코드는 `QueryServiceFromBackgroundThread` 메서드가 백그라운드 스레드에서 서비스를 가져올 서비스 공급자의 역마샬링 합니다.  
  
```  
class CMyPackage : public IVsPackage  
{  
private:  
    // Used to marshal IServiceProvider between threads  
    CComPtr< IStream > m_pSPStream;  
    // IServiceProvider proxy for the background thread  
    CComPtr< IServiceProvider > m_pBackgroundSP;  
  
public:  
    HRESULT SetSite( IServiceProvider* pSP )  
    {  
        // Marshal the service provider into a stream so that  
        // the background thread can retrieve it later  
        CoMarshalInterThreadInterfaceInStream(  
            IID_IServiceProvider, pSP, &m_pSPStream);  
  
        //... do the rest of your initialization  
    }  
  
    // Call this when your background thread needs to call QueryService  
    // The first time through, it unmarshals the interface stored   
    HRESULT QueryServiceFromBackgroundThread(  
        REFGUID rsid,        // [in] Service ID  
        REFIID riid,         // [in] Interface ID  
        // [out] Interface pointer of requested service (NULL on error)  
        void **ppvObj  
    {  
        if( !m_pBackgroundSP )  
        {  
            if( !m_pSPStream )  
            {  
                return E_UNEXPECTED;  
            }  
  
            HRESULT hr = CoGetInterfaceAndReleaseStream(   
                m_pSPStream, IID_IServiceProvider,   
                (void **)&m_pBackgroundSP );  
            if( FAILED(hr) )  
            {  
                return hr;  
            }  
  
            // The CoGetInterfaceAndReleaseStream has already   
            // destroyed the stream.  To avoid double-freeing,   
            // the smart wrapper needs to be detached.  
            m_pSPStream.Detach();  
        }  
  
        return m_pBackgroundSP->QueryService( rsid, riid, ppvObj );  
    }  
};  
```  
  
## 참고 항목  
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [서비스 Essentials](../extensibility/internals/service-essentials.md)