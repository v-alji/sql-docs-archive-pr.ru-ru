---
title: Создание веб-приложения диспетчера основных данных (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656433"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="b523d-102">Создание веб-приложения мастера основных данных (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b523d-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="b523d-103">Веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] предоставляет интерфейс пользователям для работы с основными данными, а администраторам — для настройки и администрирования MDS.</span><span class="sxs-lookup"><span data-stu-id="b523d-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="b523d-104">Веб-приложение всегда должно располагаться на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="b523d-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="b523d-105">Для создания веб-приложения можно использовать один из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b523d-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="b523d-106">Использовать веб-сайт по умолчанию, а затем создать веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="b523d-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="b523d-107">Использовать существующий веб-сайт, а затем создать веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="b523d-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="b523d-108">Создать новый веб-сайт с автоматическим созданием нового веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="b523d-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="b523d-109">После того как вы создали веб-приложение, необходимо связать его с базой данных [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b523d-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b523d-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="b523d-111">Дополнительные сведения о требованиях, предъявляемых к компьютеру, на котором размещается веб-приложение, см. в разделе [Требования веб-приложений (Master Data Services)](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b523d-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="b523d-112">Создание веб-приложения диспетчера основных данных на новом веб-сайте</span><span class="sxs-lookup"><span data-stu-id="b523d-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="b523d-113">При создании нового веб-сайта корневое веб-приложение является веб-приложением [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="b523d-114">Это веб-приложение будет также добавляется в новый пул приложений.</span><span class="sxs-lookup"><span data-stu-id="b523d-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b523d-115">При выполнении этой процедуры нельзя указать виртуальный путь и псевдоним для веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="b523d-116">Если необходимо указать виртуальный путь и псевдоним для [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], веб-приложение следует создать на существующем веб-сайте, причем он не должен быть настроен в качестве веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="b523d-117">Следует также учитывать, что [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] поддерживает создание сайтов только с HTTP-привязками.</span><span class="sxs-lookup"><span data-stu-id="b523d-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="b523d-118">Для добавления привязки HTTPS создайте новый сайт и приложение в [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] , а затем см. дополнительные сведения в разделе [Обеспечение безопасности веб-приложения диспетчера основных данных](secure-a-master-data-manager-web-application.md) .</span><span class="sxs-lookup"><span data-stu-id="b523d-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="b523d-119">Создание веб-приложения диспетчера основных данных на новом веб-сайте</span><span class="sxs-lookup"><span data-stu-id="b523d-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="b523d-120">Откройте среду [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b523d-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="b523d-121">На панели слева щелкните элемент **Веб-конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="b523d-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="b523d-122">На странице **Веб-конфигурация** в списке «Веб-сайт» выберите **Создать новый веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="b523d-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="b523d-123">В диалоговом окне **Создание веб-сайта** укажите данные для нового веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="b523d-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="b523d-124">Дополнительные сведения о параметрах пользовательского интерфейса в этом диалоговом окне см. в разделе [Диалоговое окно "Создание веб-сайта" (диспетчер конфигурации Master Data Services)](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b523d-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="b523d-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b523d-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="b523d-126">Создание веб-приложения диспетчера основных данных на существующем веб-сайте</span><span class="sxs-lookup"><span data-stu-id="b523d-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="b523d-127">При создании веб-приложения на существующем веб-сайте для него можно выбрать виртуальный путь и псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b523d-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="b523d-128">Это веб-приложение будет добавлено в новый пул приложений.</span><span class="sxs-lookup"><span data-stu-id="b523d-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="b523d-129">Создание веб-приложения диспетчера основных данных на существующем веб-сайте</span><span class="sxs-lookup"><span data-stu-id="b523d-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="b523d-130">Откройте среду [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b523d-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="b523d-131">На панели слева щелкните элемент **Веб-конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="b523d-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="b523d-132">На странице **Веб-конфигурация** в списке **Веб-сайт** выберите веб-сайт, на котором нужно создать веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="b523d-133">Нажмите кнопку **Создать приложение**.</span><span class="sxs-lookup"><span data-stu-id="b523d-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="b523d-134">В диалоговом окне **Создание веб-приложения** укажите данные для нового веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="b523d-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="b523d-135">Дополнительные сведения о параметрах пользовательского интерфейса в этом диалоговом окне см. в разделе [Диалоговое окно "Создание веб-приложения" (диспетчер конфигурации Master Data Services)](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b523d-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="b523d-136">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b523d-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b523d-137">Next Steps</span><span class="sxs-lookup"><span data-stu-id="b523d-137">Next Steps</span></span>  
  
-   <span data-ttu-id="b523d-138">Свяжите веб-приложение с базой данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b523d-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="b523d-139">Дополнительные сведения см. в разделе [Связывание базы данных служб Master Data Services и веб-приложения](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="b523d-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="b523d-140">В случае если требуется шифровать содержимое при помощи протокола SSL, на веб-сайте, содержащем веб-приложение [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] , можно настроить использование HTTPS-привязки.</span><span class="sxs-lookup"><span data-stu-id="b523d-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="b523d-141">Для настройки сертификата сервера для веб-сервера, а также настройки HTTPS-привязки и параметров SSL для сайта необходимо использовать средства служб IIS, например диспетчер IIS.</span><span class="sxs-lookup"><span data-stu-id="b523d-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="b523d-142">Дополнительные сведения см. в статье [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="b523d-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b523d-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="b523d-143">See Also</span></span>  
 [<span data-ttu-id="b523d-144">Установка служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="b523d-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
