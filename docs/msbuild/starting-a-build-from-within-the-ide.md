---
title: "IDE에서 빌드 시작 | Microsoft Docs"
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
  - "빌드"
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# IDE에서 빌드 시작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 지정 프로젝트 시스템에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor>를 사용하여 빌드를 시작해야 합니다.  이 항목에서는 이렇게 해야 하는 이유에 대해 설명하고 이렇게 하는 절차에 대해 간략하게 설명합니다.  
  
## 병렬 빌드 및 스레드  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 공용 리소스에 액세스하려면 중재가 필요한 병렬 빌드를 허용합니다.  프로젝트 시스템에서는 빌드를 비동기적으로 실행할 수 있습니다. 그러나 이러한 시스템에서는 빌드 관리자에게 제공된 콜백 내에서 빌드 함수를 호출하면 안 됩니다.  
  
 프로젝트 시스템에서 환경 변수를 수정하는 경우 빌드의 NodeAffinity를 OutOfProc로 설정해야 합니다.  이는 호스트 개체를 사용하려면 in\-proc 노드가 있어야 하기 때문에 호스트 개체를 사용할 수 없음을 의미합니다.  
  
## IVSBuildManagerAccessor 사용  
 다음 코드는 프로젝트 시스템에서 빌드를 시작하는 데 사용할 수 있는 메서드를 요약한 것입니다.  
  
```  
  
public bool Build(Project project, bool isDesignTimeBuild)  
{  
    // Get the accessor from the IServiceProvider interface for the   
    // project system  
    IVsBuildManagerAccessor accessor =  
        serviceProvider.GetService(typeof(SVsBuildManagerAccessor)) as     
        IVsBuildManagerAccessor;  
    bool releaseUIThread = false;  
    try  
    {  
        if(accessor != null)  
        {  
            // Claim the UI thread under the following conditions:  
            // 1. The build must use a resource that uses the UI thread  
            // or,  
            // 2. The build requires the in-proc node AND waits on the   
            // UI thread for the build to complete  
            if(NeedsUIThread)  
            {  
                int result = accessor.ClaimUIThreadForBuild();  
                if(result != S_OK)  
                {  
                     // Not allowed to claim the UI thread right now  
                     return false;  
                }  
                releaseUIThread = true;  
             }  
             if(isDesignTimeBuild)  
             {  
// Start the design time build  
                  int result = accessor.BeginDesignTimeBuild();  
                  if(result != S_OK)  
                  {  
                      // Not allowed to begin a design-time build at  
                      // this time. Try again later.  
                      return false;  
                  }  
             }  
         }  
         bool buildSucceeded = false;  
         // perform project-system specific build set up tasks  
         // Create your BuildRequestData  
         // This assumes a IHostServices variable (hostServices) set   
   // to your host services. If you don't use a project instance   
         // (you build from a file for example) then use another   
         // constructor.  
         BuildRequestData requestData = new   
             BuildRequestData(project.CreateProjectInstance(),   
             "myTarget", hostServices,   
             BuildRequestData.BuildRequestDataFlags.None);  
         // Mark your your submission as Pending  
         BuildSubmission submission =  
              BuildManager.DefaultBuildManager.  
              PendBuildRequest(requestData);  
         // Register the loggers in BuildLoggers  
         if (accessor != null)  
         {  
               foreach (ILogger logger in BuildLoggers)  
               {  
                    accessor.RegisterLogger(submission.SubmissionId,   
                        logger);  
               }  
         }  
         BuildResult buildResult = submission.Execute();  
         return buildResult;  
     }  
     // Clean up resources  
     finally  
     {  
         if(accessor != null)  
         {  
             // Unregister the loggers, if necessary.  
             accessor.UnregisterLoggers(submission.SubmissionId);  
             // Release the UI thread, if used  
             if(releaseUIThread)  
             {  
                  accessor.ReleaseUIThreadForBuild();  
             }  
             // End the design time build, if used  
             if(isDesignTimeBuild)  
             {  
                  accessor.EndDesignTimeBuild();  
             }  
         }  
     }  
}  
  
```