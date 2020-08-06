---
title: Экспорт политики управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664886"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="6b302-102">Экспорт политики управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="6b302-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="6b302-103">В этом разделе описывается экспорт политики управления на основе политик в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b302-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6b302-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6b302-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6b302-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6b302-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6b302-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6b302-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6b302-107">**Экспорт политики с помощью:**</span><span class="sxs-lookup"><span data-stu-id="6b302-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="6b302-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b302-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6b302-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6b302-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6b302-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="6b302-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6b302-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="6b302-111">Permissions</span></span>  
 <span data-ttu-id="6b302-112">Требуется членство в роли PolicyAdministratorRole базы данных msdb.</span><span class="sxs-lookup"><span data-stu-id="6b302-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6b302-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6b302-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="6b302-114">Экспорт политики</span><span class="sxs-lookup"><span data-stu-id="6b302-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="6b302-115">В обозревателе объектов щелкните знак «плюс», чтобы развернуть сервер, содержащий политику управления на основе политик, которую необходимо экспортировать.</span><span class="sxs-lookup"><span data-stu-id="6b302-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="6b302-116">Щелкните знак «плюс», чтобы развернуть папку **Управление** .</span><span class="sxs-lookup"><span data-stu-id="6b302-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="6b302-117">Щелкните знак «плюс», чтобы развернуть папку **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="6b302-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="6b302-118">Щелкните знак «плюс», чтобы развернуть папку **Политики** .</span><span class="sxs-lookup"><span data-stu-id="6b302-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="6b302-119">Щелкните правой кнопкой мыши политику, которую необходимо экспортировать, а затем выберите пункт **Экспортировать политику**.</span><span class="sxs-lookup"><span data-stu-id="6b302-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="6b302-120">В диалоговом окне **Экспорт политики** введите в адресной строке имя файла и путь к нему.</span><span class="sxs-lookup"><span data-stu-id="6b302-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="6b302-121">Также можно найти подходящее расположение для файла в области панели навигации диалогового окна, а затем ввести имя XML-файла в поле **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="6b302-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="6b302-122">По завершении щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6b302-122">When finished, click **Save**.</span></span>  
  
  
