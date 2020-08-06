---
title: Импорт политики управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655694"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="6abc5-102">Импорт политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="6abc5-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="6abc5-103">В этом разделе описывается импорт экземпляра политики управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6abc5-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6abc5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6abc5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6abc5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6abc5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6abc5-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6abc5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6abc5-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6abc5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6abc5-108">**Импорт экземпляра политики с помощью:**</span><span class="sxs-lookup"><span data-stu-id="6abc5-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="6abc5-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6abc5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6abc5-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6abc5-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6abc5-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6abc5-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6abc5-112">поставляется с политиками, которые можно использовать для наблюдения за экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6abc5-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6abc5-113">По умолчанию эти политики не устанавливаются в компоненте [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], однако их можно импортировать из места установки по умолчанию — «C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033».</span><span class="sxs-lookup"><span data-stu-id="6abc5-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6abc5-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="6abc5-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6abc5-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="6abc5-115">Permissions</span></span>  
 <span data-ttu-id="6abc5-116">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="6abc5-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6abc5-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6abc5-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="6abc5-118">Импорт экземпляра политики</span><span class="sxs-lookup"><span data-stu-id="6abc5-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="6abc5-119">В **обозревателе объектов**щелкните знак "плюс", чтобы развернуть сервер, где будет располагаться импортируемый экземпляр политики.</span><span class="sxs-lookup"><span data-stu-id="6abc5-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="6abc5-120">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="6abc5-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6abc5-121">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="6abc5-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6abc5-122">Щелкните правой кнопкой мыши папку **Политики** и выберите команду **Импорт политики**.</span><span class="sxs-lookup"><span data-stu-id="6abc5-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="6abc5-123">Введите имя и путь к файлу в диалоговом окне **Импортировать** либо найдите XML-файл, содержащий политику, при помощи кнопки (**Обзор...** ) и выберите его.</span><span class="sxs-lookup"><span data-stu-id="6abc5-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="6abc5-124">Дополнительные сведения о параметрах, доступных в диалоговом окне **Импорт** , см. в разделе [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="6abc5-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="6abc5-125">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6abc5-125">When finished, click **OK**.</span></span>  
  
  
