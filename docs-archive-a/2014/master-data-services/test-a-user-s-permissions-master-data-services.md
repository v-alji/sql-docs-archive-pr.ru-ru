---
title: Проверка разрешений пользователя (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664966"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="80ae4-102">Проверка разрешений пользователя (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="80ae4-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="80ae4-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно создать тестовую учетную запись и войти в веб-приложение для проверки разрешений. При попытке пользователя получить доступ к URL-адресу [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выполняется проверка учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="80ae4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="80ae4-104">В Internet Explorer в зависимости от параметров безопасности проверка подлинности будет выполнена автоматически либо пользователю придется ввести имя и пароль.</span><span class="sxs-lookup"><span data-stu-id="80ae4-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="80ae4-105">Чтобы изменить эти настройки, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="80ae4-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="80ae4-106">Проверка безопасности пользователя</span><span class="sxs-lookup"><span data-stu-id="80ae4-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="80ae4-107">В Internet Explorer версии 7 и выше выберите в меню **Сервис**пункт **Свойства обозревателя**и перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="80ae4-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="80ae4-108">Нажмите **Местная интрасеть** , затем нажмите кнопку **Другой** .</span><span class="sxs-lookup"><span data-stu-id="80ae4-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="80ae4-109">В разделе **Проверка подлинности пользователя** выберите **Запрос имени пользователя и пароля**.</span><span class="sxs-lookup"><span data-stu-id="80ae4-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="80ae4-110">При следующем открытии окна браузера будет предложено указать имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="80ae4-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ae4-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="80ae4-111">See Also</span></span>  
 [<span data-ttu-id="80ae4-112">Безопасность (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="80ae4-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
