# [MsBuild](msbuild.md)

## [MSBuild 15.0의 새로운 기능](what-s-new-in-msbuild-15-0.md)

## [MSBuild 개념](msbuild-concepts.md)

### [MSBuild 속성](msbuild-properties.md)

#### [방법: 빌드 시 환경 변수 사용](how-to-use-environment-variables-in-a-build.md)

#### [방법: 프로젝트 파일의 이름 또는 위치 참조](how-to-reference-the-name-or-location-of-the-project-file.md)

#### [방법: 동일한 소스 파일을 다른 옵션을 사용하여 빌드](how-to-build-the-same-source-files-with-different-options.md)

#### [속성 함수](property-functions.md)

### [MSBuild 항목](msbuild-items.md)

#### [방법: 빌드할 파일 선택](how-to-select-the-files-to-build.md)

#### [방법: 빌드에서 파일 제외](how-to-exclude-files-from-the-build.md)

#### [방법: 항목 목록을 쉼표로 구분하여 표시](how-to-display-an-item-list-separated-with-commas.md)

#### [항목 정의](item-definitions.md)

#### [항목 함수](item-functions.md)

#### [파일 추적](file-tracking.md)

##### [EndTrackingContext](endtrackingcontext.md)

##### [ResumeTracking](resumetracking.md)

##### [SetThreadCount](setthreadcount.md)

##### [StartTrackingContext](starttrackingcontext.md)

##### [StartTrackingContextWithRoot](starttrackingcontextwithroot.md)

##### [StopTrackingAndCleanup](stoptrackingandcleanup.md)

##### [SuspendTracking](suspendtracking.md)

##### [WriteAllTLogs](writealltlogs.md)

##### [WriteContextTLogs](writecontexttlogs.md)

### [MSBuild 대상](msbuild-targets.md)

#### [대상 빌드 순서](target-build-order.md)

#### [증분 빌드](incremental-builds.md)

#### [방법: 먼저 빌드할 대상 지정](how-to-specify-which-target-to-build-first.md)

#### [방법: 여러 프로젝트 파일에서 동일한 대상 사용](how-to-use-the-same-target-in-multiple-project-files.md)

#### [방법: MSBuild.exe를 사용하여 솔루션의 특정 대상 빌드](how-to-build-specific-targets-in-solutions-by-using-msbuild-exe.md)

#### [방법: 증분 빌드](how-to-build-incrementally.md)

#### [방법: 빌드 정리](how-to-clean-a-build.md)

### [MSBuild 작업](msbuild-tasks.md)

#### [작업 작성](task-writing.md)

#### [방법: 작업의 오류 무시](how-to-ignore-errors-in-tasks.md)

#### [방법: 리소스를 사용하는 프로젝트 빌드](how-to-build-a-project-that-has-resources.md)

#### [MSBuild 인라인 작업](msbuild-inline-tasks.md)

##### [연습: 인라인 작업 만들기](walkthrough-creating-an-inline-task.md)

### [속성 및 항목 비교](comparing-properties-and-items.md)

### [MSBuild 특수 문자](msbuild-special-characters.md)

#### [방법: MSBuild의 이스케이프 특수 문자](how-to-escape-special-characters-in-msbuild.md)

#### [방법: 프로젝트 파일에서 예약된 XML 문자 사용](how-to-use-reserved-xml-characters-in-project-files.md)

## [MSBuild 고급 개념](msbuild-advanced-concepts.md)

### [MSBuild 일괄 처리](msbuild-batching.md)

#### [작업 일괄 처리의 항목 메타데이터](item-metadata-in-task-batching.md)

#### [대상 일괄 처리의 항목 메타데이터](item-metadata-in-target-batching.md)

### [MSBuild 변형](msbuild-transforms.md)

### [Visual Studio 통합(MSBuild)](visual-studio-integration-msbuild.md)

#### [방법: Visual Studio 빌드 프로세스 확장](how-to-extend-the-visual-studio-build-process.md)

#### [IDE에서 빌드 시작](starting-a-build-from-within-the-ide.md)

#### [.NET Framework 확장명 등록](registering-extensions-of-the-dotnet-framework.md)

### [MSBuild를 사용하여 병렬로 여러 프로젝트 빌드](building-multiple-projects-in-parallel-with-msbuild.md)

#### [다중 프로세서를 사용하여 프로젝트 빌드](using-multiple-processors-to-build-projects.md)

#### [대규모 프로젝트 빌드 시 메모리의 효율적인 사용](using-memory-efficiently-when-you-build-large-projects.md)

### [MSBuild 멀티 타기팅 개요](msbuild-multitargeting-overview.md)

#### [MSBuild 도구 집합(ToolsVersion)](msbuild-toolset-toolsversion.md)

##### [표준 및 사용자 지정 도구 집합 구성](standard-and-custom-toolset-configurations.md)

##### [ToolsVersion 설정 재정의](overriding-toolsversion-settings.md)

#### [MSBuild 대상 프레임워크 및 대상 플랫폼](msbuild-target-framework-and-target-platform.md)

#### [디자인 타임에 어셈블리 확인](resolving-assemblies-at-design-time.md)

#### [대상 및 작업 구성](configuring-targets-and-tasks.md)

##### [방법: 대상 및 작업 구성](how-to-configure-targets-and-tasks.md)

#### [.NET Framework 타기팅 오류 문제 해결](troubleshooting-dotnet-framework-targeting-errors.md)

### [빌드 사용자 지정](customize-your-build.md)

### [MSBuild 모범 사례](msbuild-best-practices.md)

## [MSBuildd의 로그인](logging-in-msbuild.md)

### [MSBuild를 사용하여 빌드 로그 가져오기](obtaining-build-logs-with-msbuild.md)

### [빌드 로거](build-loggers.md)

### [다중 프로세서 환경에서의 로그인](logging-in-a-multi-processor-environment.md)

### [다중 프로세서 인식 로거 작성](writing-multi-processor-aware-loggers.md)

### [전달 로거 만들기](creating-forwarding-loggers.md)

## [연습: MSBuild 사용](walkthrough-using-msbuild.md)

## [연습: 처음부터 새로 MSBuild 프로젝트 파일 만들기](walkthrough-creating-an-msbuild-project-file-from-scratch.md)

## [MSBuild 참조](msbuild-reference.md)

### [MSBuild 프로젝트 파일 스키마 참조](msbuild-project-file-schema-reference.md)

#### [Choose 요소(MSBuild)](choose-element-msbuild.md)

#### [Import 요소(MSBuild)](import-element-msbuild.md)

#### [ImportGroup 요소](importgroup-element.md)

#### [Item 요소(MSBuild)](item-element-msbuild.md)

#### [ItemDefinitionGroup 요소(MSBuild)](itemdefinitiongroup-element-msbuild.md)

#### [ItemGroup 요소(MSBuild)](itemgroup-element-msbuild.md)

#### [ItemMetadata 요소(MSBuild)](itemmetadata-element-msbuild.md)

#### [OnError 요소(MSBuild)](onerror-element-msbuild.md)

#### [Otherwise 요소(MSBuild)](otherwise-element-msbuild.md)

#### [Output 요소(MSBuild)](output-element-msbuild.md)

#### [Parameter 요소](parameter-element.md)

#### [ParameterGroup 요소](parametergroup-element.md)

#### [Project 요소(MSBuild)](project-element-msbuild.md)

#### [ProjectExtensions 요소(MSBuild)](projectextensions-element-msbuild.md)

#### [Property 요소(MSBuild)](property-element-msbuild.md)

#### [PropertyGroup 요소(MSBuild)](propertygroup-element-msbuild.md)

#### [Target 요소(MSBuild)](target-element-msbuild.md)

#### [Task 요소(MSBuild)](task-element-msbuild.md)

#### [TaskBody 요소(MSBuild)](taskbody-element-msbuild.md)

#### [UsingTask 요소(MSBuild)](usingtask-element-msbuild.md)

#### [When 요소(MSBuild)](when-element-msbuild.md)

### [MSBuild 작업 참조](msbuild-task-reference.md)

#### [Visaul C++ 관련 MSBuild 작업](msbuild-tasks-specific-to-visual-cpp.md)

##### [BscMake 작업](bscmake-task.md)

##### [CL 작업](cl-task.md)

##### [CPPClean 작업](cppclean-task.md)

##### [LIB 작업](lib-task.md)

##### [링크 작업](link-task.md)

##### [MIDL 작업](midl-task.md)

##### [MT 작업](mt-task.md)

##### [RC 작업](rc-task.md)

##### [SetEnv 작업](setenv-task.md)

##### [VCMessage 작업](vcmessage-task.md)

##### [XDCMake 작업](xdcmake-task.md)

##### [XSD 작업](xsd-task.md)

#### [Task 기본 클래스](task-base-class.md)

#### [TaskExtension 기본 클래스](taskextension-base-class.md)

#### [ToolTaskExtension 기본 클래스](tooltaskextension-base-class.md)

#### [AL(어셈블리 링커) 작업](al-assembly-linker-task.md)

#### [AspNetCompiler 작업](aspnetcompiler-task.md)

#### [AssignCulture 작업](assignculture-task.md)

#### [AssignProjectConfiguration 작업](assignprojectconfiguration-task.md)

#### [AssignTargetPath 작업](assigntargetpath-task.md)

#### [CallTarget 작업](calltarget-task.md)

#### [CombinePath 작업](combinepath-task.md)

#### [ConvertToAbsolutePath 작업](converttoabsolutepath-task.md)

#### [Copy 작업](copy-task.md)

#### [CreateCSharpManifestResourceName 작업](createcsharpmanifestresourcename-task.md)

#### [CreateItem 작업](createitem-task.md)

#### [CreateProperty 작업](createproperty-task.md)

#### [CreateVisualBasicManifestResourceName 작업](createvisualbasicmanifestresourcename-task.md)

#### [Csc 작업](csc-task.md)

#### [Delete 작업](delete-task.md)

#### [Error 작업](error-task.md)

#### [Exec 작업](exec-task.md)

#### [FindAppConfigFile 작업](findappconfigfile-task.md)

#### [FindInList 작업](findinlist-task.md)

#### [FindUnderPath 작업](findunderpath-task.md)

#### [FormatUrl 작업](formaturl-task.md)

#### [FormatVersion 작업](formatversion-task.md)

#### [GenerateApplicationManifest 작업](generateapplicationmanifest-task.md)

#### [GenerateBootstrapper 작업](generatebootstrapper-task.md)

#### [GenerateDeploymentManifest 작업](generatedeploymentmanifest-task.md)

#### [GenerateResource 작업](generateresource-task.md)

#### [GenerateTrustInfo 작업](generatetrustinfo-task.md)

#### [GetAssemblyIdentity 작업](getassemblyidentity-task.md)

#### [GetFrameworkPath 작업](getframeworkpath-task.md)

#### [GetFrameworkSdkPath 작업](getframeworksdkpath-task.md)

#### [GetReferenceAssemblyPaths 작업](getreferenceassemblypaths-task.md)

#### [LC 작업](lc-task.md)

#### [MakeDir 작업](makedir-task.md)

#### [Message 작업](message-task.md)

#### [Move 작업](move-task.md)

#### [MSBuild 작업](msbuild-task.md)

#### [ReadLinesFromFile 작업](readlinesfromfile-task.md)

#### [RegisterAssembly 작업](registerassembly-task.md)

#### [RemoveDir 작업](removedir-task.md)

#### [RemoveDuplicates 작업](removeduplicates-task.md)

#### [RequiresFramework35SP1Assembly 작업](requiresframework35sp1assembly-task.md)

#### [ResolveAssemblyReference 작업](resolveassemblyreference-task.md)

#### [ResolveComReference 작업](resolvecomreference-task.md)

#### [ResolveKeySource 작업](resolvekeysource-task.md)

#### [ResolveManifestFiles 작업](resolvemanifestfiles-task.md)

#### [ResolveNativeReference 작업](resolvenativereference-task.md)

#### [ResolveNonMSBuildProjectOutput 작업](resolvenonmsbuildprojectoutput-task.md)

#### [SGen 작업](sgen-task.md)

#### [SignFile 작업](signfile-task.md)

#### [Touch 작업](touch-task.md)

#### [UnregisterAssembly 작업](unregisterassembly-task.md)

#### [UpdateManifest 작업](updatemanifest-task.md)

#### [Vbc 작업](vbc-task.md)

#### [Warning 작업](warning-task.md)

#### [WriteCodeFragment 작업](writecodefragment-task.md)

#### [WriteLinesToFile 작업](writelinestofile-task.md)

#### [XmlPeek 작업](xmlpeek-task.md)

#### [XmlPoke 작업](xmlpoke-task.md)

#### [XslTransformation 작업](xsltransformation-task.md)

### [MSBuild 조건](msbuild-conditions.md)

### [MSBuild 조건부 구문](msbuild-conditional-constructs.md)

### [MSBuild의 예약된 속성 및 잘 알려진 속성](msbuild-reserved-and-well-known-properties.md)

### [일반적인 MSBuild 프로젝트 속성](common-msbuild-project-properties.md)

### [일반적인 MSBuild 프로젝트 항목](common-msbuild-project-items.md)

### [MSBuild 명령줄 참조](msbuild-command-line-reference.md)

### [MSBuild .Targets 파일](msbuild-dot-targets-files.md)

### [MSBuild 잘 알려진 항목 메타데이터](msbuild-well-known-item-metadata.md)

### [MSBuild 지시 파일](msbuild-response-files.md)

### [WPF MSBuild 참조](wpf-msbuild-reference.md)

#### [WPF .Targets 파일](wpf-dot-targets-files.md)

#### [WPF MSBuild 작업 참조](wpf-msbuild-task-reference.md)

##### [FileClassifier 작업](fileclassifier-task.md)

##### [GenerateTemporaryTargetAssembly 작업](generatetemporarytargetassembly-task.md)

##### [GetWinFXPath 작업](getwinfxpath-task.md)

##### [MarkupCompilePass1 작업](markupcompilepass1-task.md)

##### [MarkupCompilePass2 작업](markupcompilepass2-task.md)

##### [MergeLocalizationDirectives 작업](mergelocalizationdirectives-task.md)

##### [ResourcesGenerator 작업](resourcesgenerator-task.md)

##### [UidManager 작업](uidmanager-task.md)

##### [UpdateManifestForBrowserApplication 작업](updatemanifestforbrowserapplication-task.md)

### [이스케이프할 특수 문자](special-characters-to-escape.md)

## [MSBuild 용어](msbuild-glossary.md)

