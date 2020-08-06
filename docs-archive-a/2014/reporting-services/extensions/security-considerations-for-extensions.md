---
title: Рекомендации по обеспечению безопасности модулей | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- extensions [Reporting Services], security
- permissions [Reporting Services], extensions
ms.assetid: 58cbdfeb-1105-4a7d-a3b8-b897ff95f367
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e7819f4d6de2003c9982d33ab00cfa0d4030aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668654"
---
# <a name="security-considerations-for-extensions"></a><span data-ttu-id="ca964-102">Вопросы безопасности для модулей</span><span class="sxs-lookup"><span data-stu-id="ca964-102">Security Considerations for Extensions</span></span>
  <span data-ttu-id="ca964-103">Все приложения, предназначенные для работы в среде CLR, должны взаимодействовать с системой безопасности этой среды.</span><span class="sxs-lookup"><span data-stu-id="ca964-103">Every application that targets the common language runtime (CLR) must interact with the CLR security system.</span></span> <span data-ttu-id="ca964-104">Такое приложение после вызова на выполнение автоматически проверяется средой CLR и получает от CLR набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="ca964-104">When such an application runs, it is automatically evaluated and given a set of permissions by the CLR.</span></span> <span data-ttu-id="ca964-105">В зависимости от полученных разрешений приложение либо продолжает свою работу, либо вырабатывает исключение безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca964-105">Depending on the permissions that the application receives, it either continues running or generates a security exception.</span></span> <span data-ttu-id="ca964-106">Разрешения для кода, получаемые сборкой, определяются локальными параметрами безопасности и политиками в файлах конфигурации политики безопасности для конкретного сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ca964-106">The local security settings and policies in the security policy configuration files for a particular report server define the code permissions that an assembly receives.</span></span>  
  
 <span data-ttu-id="ca964-107">Прежде чем запрашивать разрешения, необходимо определить, какие ресурсы и защищенные операции намечено использовать в коде модуля, а также знать о том, какие разрешения применяются для защиты этих ресурсов и операций.</span><span class="sxs-lookup"><span data-stu-id="ca964-107">Before requesting permissions, you need to be aware of the resources and protected operations your extension code is planning to use, and you also need to know which permissions protect those resources and operations.</span></span> <span data-ttu-id="ca964-108">Кроме того, необходимо следить за всеми ресурсами, доступ к которым получают любые методы библиотеки классов, вызываемые компонентами модуля.</span><span class="sxs-lookup"><span data-stu-id="ca964-108">In addition, you need to keep track of any resources accessed by any class library methods that are called by the extension components.</span></span> <span data-ttu-id="ca964-109">Дополнительные сведения см. в разделе «Запрос на разрешения» документа «Руководство разработчика [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]».</span><span class="sxs-lookup"><span data-stu-id="ca964-109">For more information, see "Requesting Permissions" in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="ca964-110">Модули, развернутые на сервере отчетов, должны использоваться как полностью доверенные, а это означает, что модуль должен входить в состав группы кода, которой предоставлен набор разрешений **FullTrust**.</span><span class="sxs-lookup"><span data-stu-id="ca964-110">Extensions deployed to a report server must run as fully trusted, meaning that your extension needs to be part of a code group that is granted the **FullTrust** permission set.</span></span> <span data-ttu-id="ca964-111">Это также означает, что модуль может иметь доступ к определенным ресурсам и операциям сервера, предоставляемым средой CLR, в зависимости от того, какой пользователь прошел проверку подлинности для работы с конкретным отчетом.</span><span class="sxs-lookup"><span data-stu-id="ca964-111">This also means that your extension may have access to certain server resources and operations available through the CLR depending on the user that is being authenticated for a particular report.</span></span> <span data-ttu-id="ca964-112">Дополнительные сведения о группах кода и модулях см. в статье [Управление доступом для кода в службах Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca964-112">For more information about code groups and extensions, see [Code Access Security in Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ca964-113">В службе [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] принудительно применяется режим безопасности [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] для всех собственных модулей.</span><span class="sxs-lookup"><span data-stu-id="ca964-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enforces [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security for all of its extensions.</span></span>  
  
 <span data-ttu-id="ca964-114">При развертывании модулей обработки данных, доставки, подготовки к отображению и безопасности службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] должны соблюдаться следующие условия:</span><span class="sxs-lookup"><span data-stu-id="ca964-114">The following conditions apply to the deployment of data processing, delivery, rendering, and security extensions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="ca964-115">Разрешение на развертывание модуля имеет только местный администратор.</span><span class="sxs-lookup"><span data-stu-id="ca964-115">Only the local administrator has permission to deploy an extension.</span></span>  
  
-   <span data-ttu-id="ca964-116">Файлы конфигурации для расширяемого компонента [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] могут изменять только пользователи с соответствующими разрешениями на чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="ca964-116">Only users with the appropriate read/write permissions can change the configuration files for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component that is being extended.</span></span>  
  
-   <span data-ttu-id="ca964-117">Изменять файлы политики безопасности и включать управление доступом для модуля разрешается только привилегированным пользователям.</span><span class="sxs-lookup"><span data-stu-id="ca964-117">Only privileged users have permission to edit the security policy files and enable code access security for an extension.</span></span>  
  
 <span data-ttu-id="ca964-118">Дополнительные сведения о безопасном управлении доступом для кода в [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] см. в разделе [Безопасная разработка (службы Reporting Services)](secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ca964-118">For more information about code access security in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](secure-development/secure-development-reporting-services.md).</span></span>  
  
 <span data-ttu-id="ca964-119">Дополнительные сведения о средствах безопасности [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] см. в разделе «Безопасность .NET Framework» документа «Руководство разработчика [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]».</span><span class="sxs-lookup"><span data-stu-id="ca964-119">For more information about [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security, see ".NET Framework Security" in your [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
## <a name="initialization-of-extension-assemblies"></a><span data-ttu-id="ca964-120">Инициализация сборок модуля</span><span class="sxs-lookup"><span data-stu-id="ca964-120">Initialization of Extension Assemblies</span></span>  
 <span data-ttu-id="ca964-121">При первоначальной загрузке сервером отчетов модулей в память в них используются учетные данные этой службы, поскольку некоторым сборкам модулей требуются специальные разрешения для доступа к системным ресурсам, чтения файлов конфигурации и загрузки других, зависимых сборок.</span><span class="sxs-lookup"><span data-stu-id="ca964-121">When extensions are first loaded into memory by the report server, they use the service account credentials, because some extension assemblies require specific permissions to access system resources, to read configuration files, and to load other, dependent assemblies.</span></span> <span data-ttu-id="ca964-122">Но после загрузки и инициализации сборки все последующие вызовы сборок модуля осуществляются с использованием учетных данных пользователя, который в данный момент зарегистрирован в системе.</span><span class="sxs-lookup"><span data-stu-id="ca964-122">After an assembly has been loaded and initialized, however, all subsequent calls to extension assemblies use the credentials of the user account that is currently logged on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca964-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca964-123">See Also</span></span>  
 <span data-ttu-id="ca964-124">[Модули служб Reporting Services](reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="ca964-124">[Reporting Services Extensions](reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="ca964-125">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ca964-125">Reporting Services Extension Library</span></span>](reporting-services-extension-library.md)  
  
  
