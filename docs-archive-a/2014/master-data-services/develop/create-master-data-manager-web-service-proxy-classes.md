---
title: Создание прокси-классов веб-службы диспетчера основных данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669442"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="f9ed1-102">Создание классов-посредников веб-службы диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="f9ed1-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="f9ed1-103">Веб-служба [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] позволяет программно использовать функции [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] с любого компьютера, имеющего доступ к веб-сайту [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9ed1-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="f9ed1-104">Перед тем как писать код для доступа к веб-службе, необходимо создать классы-посредники.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="f9ed1-105">Основным классом-посредником, который используется для выполнения операций веб-службы, является класс <xref:Microsoft.MasterDataServices.ServiceClient>, реализующий интерфейс <xref:Microsoft.MasterDataServices.IService>.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="f9ed1-106">Включение публикации метаданных веб-службы</span><span class="sxs-lookup"><span data-stu-id="f9ed1-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="f9ed1-107">Перед созданием классов-посредников необходимо включить публикацию метаданных веб-службы.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="f9ed1-108">Для этого выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="f9ed1-109">Откройте файл Web.config [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="f9ed1-110">Этот файл находится в папке WebApplication каталога пути установки [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ed1-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="f9ed1-111">Найдите `mdsWsHttpBehavior` раздел в разделе **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="f9ed1-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="f9ed1-112">Для **\<serviceMetadata>** элемента задайте значение `httpGetEnabled` `true` .</span><span class="sxs-lookup"><span data-stu-id="f9ed1-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9ed1-113">Чтобы включить веб-службы по протоколу SSL, задайте свойству `httpsGetEnabled` значение `true` в секции `mdsWsHttpBehavior` файла web.config.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="f9ed1-114">Необходимо также настроить `mdsWsHTTPBinding` на протокол SSL и закомментировать секцию не SSL.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="f9ed1-115">Сохраните изменения в файле.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="f9ed1-116">Для проверки публикации метаданных перейдите по URL-адресу службы, например: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="f9ed1-117">Если публикация метаданных включена, то на экране появится страница, которая начинается со слов</span><span class="sxs-lookup"><span data-stu-id="f9ed1-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="f9ed1-118">"Вы создали службу".</span><span class="sxs-lookup"><span data-stu-id="f9ed1-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="f9ed1-119">Создание классов-посредников с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9ed1-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="f9ed1-120">Если установлена программа Visual Studio 2010, то самый простой способ создания прокси-классов заключается в добавлении в проект **Ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="f9ed1-121">Адресом ссылки на службу является URL-адрес веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], к которому добавлено /service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="f9ed1-122">Например: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="f9ed1-123">Дополнительные сведения см. в статье [Добавление, обновление или удаление ссылки на службу](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="f9ed1-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="f9ed1-124">Создание классов-посредников с помощью Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="f9ed1-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="f9ed1-125">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] Для Svcutil.exe на компьютере необходимо установить или Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="f9ed1-126">При использовании среды [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для выполнения команды необходимо использовать командную строку [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ed1-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="f9ed1-127">Дополнительные сведения см. в статьях [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) (Служебная программа для работы с метаданными ServiceModel — Svcutil.exe) и [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821) (Создание клиента WCF из метаданных службы).</span><span class="sxs-lookup"><span data-stu-id="f9ed1-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="f9ed1-128">Для создания набора классов-посредников C# с помощью Svcutil.exe используйте команду наподобие следующей:</span><span class="sxs-lookup"><span data-stu-id="f9ed1-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="f9ed1-129">Где:</span><span class="sxs-lookup"><span data-stu-id="f9ed1-129">Where:</span></span>  
  
-   <span data-ttu-id="f9ed1-130">*servername*:*port* — это имя компьютера и номер порта компьютера, на котором размещаются службы [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ed1-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="f9ed1-131">*virtual_path* — это виртуальный путь к службам [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] в службах Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="f9ed1-132">*proxy_name* ― это имя создаваемого прокси-файла.</span><span class="sxs-lookup"><span data-stu-id="f9ed1-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ed1-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9ed1-133">See Also</span></span>  
 [<span data-ttu-id="f9ed1-134">Операции веб-службы по категориям (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f9ed1-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
