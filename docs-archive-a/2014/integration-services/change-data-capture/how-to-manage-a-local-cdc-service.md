---
title: Как управлять локальной службой CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727313"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="d45d5-102">Как управлять локальной службой CDC</span><span class="sxs-lookup"><span data-stu-id="d45d5-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="d45d5-103">В этой процедуре описывается использование консоли настройки службы CDC для управления конкретными службами CDC.</span><span class="sxs-lookup"><span data-stu-id="d45d5-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="d45d5-104">Управление конкретной службой CDC</span><span class="sxs-lookup"><span data-stu-id="d45d5-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="d45d5-105">В меню **Пуск** выберите пункт **Конфигурация служб CDC для Oracle**.</span><span class="sxs-lookup"><span data-stu-id="d45d5-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="d45d5-106">На левой панели консоли настройки службы CDC разверните список **Локальные службы CDC**.</span><span class="sxs-lookup"><span data-stu-id="d45d5-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="d45d5-107">Выберите службу CDC, с которой требуется выполнить действия.</span><span class="sxs-lookup"><span data-stu-id="d45d5-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="d45d5-108">Также можно щелкнуть правой кнопкой мыши службу CDC, с которой требуется начать работу, и выбрать нужное действие.</span><span class="sxs-lookup"><span data-stu-id="d45d5-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="d45d5-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="d45d5-109">**OR**</span></span>  
  
     <span data-ttu-id="d45d5-110">На левой панели консоли настройки службы CDC выберите пункт **Локальные службы CDC** и в средней части консоли настройки службы CDC выберите службу, с которой необходимо начать работу.</span><span class="sxs-lookup"><span data-stu-id="d45d5-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="d45d5-111">Также можно щелкнуть правой кнопкой мыши службу CDC, с которой требуется начать работу, и выбрать нужное действие.</span><span class="sxs-lookup"><span data-stu-id="d45d5-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="d45d5-112">При работе со службой CDC можно выполнять следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="d45d5-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="d45d5-113">**Удаление службы**</span><span class="sxs-lookup"><span data-stu-id="d45d5-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="d45d5-114">На панели **Действия** в правой стороне консоли настройки службы CDC щелкните **Удалить** , чтобы удалить службу.</span><span class="sxs-lookup"><span data-stu-id="d45d5-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="d45d5-115">Можно также щелкнуть правой кнопкой мыши службу CDC, которую необходимо удалить, и выбрать команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d45d5-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="d45d5-116">**Примечание**. Если на момент удаления службы она запущена, перед удалением выполняется ее остановка.</span><span class="sxs-lookup"><span data-stu-id="d45d5-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="d45d5-117">Чтобы удалить определение службы Windows для Oracle CDC, программе нужен доступ в режиме UPDATE к базе данных MSXDBCDC в соответствующем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d45d5-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d45d5-118">После нажатия кнопки **ОК** для удаления службы программа попытается выполнить удаление регистрации службы Oracle CDC в базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="d45d5-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="d45d5-119">При ошибке, возникающей из-за отсутствия необходимых разрешений, отображается диалоговое окно ввода имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с правами доступа к базе данных MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="d45d5-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="d45d5-120">Дополнительные сведения о вводе данных в диалоговом окне «Подключение к SQL Server» см. в разделах [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) и [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="d45d5-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="d45d5-121">**Изменение свойств службы CDC**</span><span class="sxs-lookup"><span data-stu-id="d45d5-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="d45d5-122">На панели **Действия** в правой стороне консоли настройки службы CDC щелкните пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d45d5-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="d45d5-123">Также можно щелкнуть правой кнопкой мыши службу CDC, свойства которой требуется изменить, и выбрать команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d45d5-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45d5-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="d45d5-124">See Also</span></span>  
 [<span data-ttu-id="d45d5-125">Управление службой CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="d45d5-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
