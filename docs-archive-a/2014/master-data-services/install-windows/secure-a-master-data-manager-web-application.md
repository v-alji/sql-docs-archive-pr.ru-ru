---
title: Обеспечение безопасности веб-приложения диспетчера основных данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738498"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="539d5-102">Обеспечение безопасности веб-приложения диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="539d5-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="539d5-103">Веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] можно обезопасить с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="539d5-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="539d5-104">Веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] может использовать протокол HTTP или HTTPS, но не оба.</span><span class="sxs-lookup"><span data-stu-id="539d5-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="539d5-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="539d5-105">Prerequisites</span></span>  
 <span data-ttu-id="539d5-106">Выполнение процедуры</span><span class="sxs-lookup"><span data-stu-id="539d5-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="539d5-107">На веб-сервере, где установлен экземпляр служб [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] , нужно обладать правами администратора.</span><span class="sxs-lookup"><span data-stu-id="539d5-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="539d5-108">Службы MDS должны быть установлены на веб-сервере, а веб-приложение должно существовать.</span><span class="sxs-lookup"><span data-stu-id="539d5-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="539d5-109">Дополнительные сведения см. в статьях [Установка служб Master Data Services](install-master-data-services.md) и [Создание веб-приложения мастера основных данных (службы Master Data Services)](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="539d5-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="539d5-110">Обеспечение безопасности веб-приложения диспетчера основных данных с помощью протокола HTTPS</span><span class="sxs-lookup"><span data-stu-id="539d5-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="539d5-111">После подтверждения того, что веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] имеет верные настройки протокола HTTP, создайте сертификат на сервере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="539d5-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="539d5-112">Дополнительные сведения см. в разделе [Настройка сертификатов сервера IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="539d5-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="539d5-113">На панели **Соединения** на вкладке **Сайты**щелкните сайт, на котором размещено веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="539d5-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="539d5-114">В области **Действия** щелкните элемент **Привязки**.</span><span class="sxs-lookup"><span data-stu-id="539d5-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="539d5-115">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="539d5-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="539d5-116">Выберите **https**из списка.</span><span class="sxs-lookup"><span data-stu-id="539d5-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="539d5-117">Выберите SSL-сертификат.</span><span class="sxs-lookup"><span data-stu-id="539d5-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="539d5-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="539d5-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="539d5-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="539d5-119">Optional.</span></span> <span data-ttu-id="539d5-120">Чтобы удалить из списка протокол HTTP, разрешив доступ к сайту только по протоколу HTTPS, щелкните строку **http**.</span><span class="sxs-lookup"><span data-stu-id="539d5-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="539d5-121">Нажмите кнопку **Удалить** и в диалоговом окне подтверждения выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="539d5-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="539d5-122">Необходимо изменить настройки basicHttp и wsHttpBinding после удаления HTTP.</span><span class="sxs-lookup"><span data-stu-id="539d5-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="539d5-123">Чтобы закрыть диалоговое окно **Привязки сайтов** , нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="539d5-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="539d5-124">Теперь откройте web.config файл с *диска*: \PROGRAM Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span><span class="sxs-lookup"><span data-stu-id="539d5-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="539d5-125">Найдите строку `<security mode="Message">` и измените ее на строку `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="539d5-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="539d5-126">Сохраните файл и закройте его.</span><span class="sxs-lookup"><span data-stu-id="539d5-126">Save and close the file.</span></span> <span data-ttu-id="539d5-127">Если возникает ошибка, это происходит из-за включенного контроля учетных записей.</span><span class="sxs-lookup"><span data-stu-id="539d5-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="539d5-128">Дополнительные сведения см. в разделе [Отключение контроля учетных записей](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="539d5-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="539d5-129">Теперь пользователи могут использовать для доступа к сайту протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="539d5-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539d5-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="539d5-130">See Also</span></span>  
 [<span data-ttu-id="539d5-131">Создание веб-приложения мастера основных данных (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="539d5-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
