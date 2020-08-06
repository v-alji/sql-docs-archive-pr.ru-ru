---
title: Управление экземпляром CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728606"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="a23b0-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="a23b0-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="a23b0-103">Эта процедура описывает управление операциями экземпляра CDC во время выполнения с помощью консоли конструктора CDC.</span><span class="sxs-lookup"><span data-stu-id="a23b0-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="a23b0-104">Управление операциями экземпляра CDC</span><span class="sxs-lookup"><span data-stu-id="a23b0-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="a23b0-105">В меню **Пуск** выберите **Консоль конструктора CDC**.</span><span class="sxs-lookup"><span data-stu-id="a23b0-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="a23b0-106">На панели слева разверните узел **Отслеживание измененных данных** , а затем разверните службу, содержащую экземпляр, данные которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a23b0-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="a23b0-107">Выберите имя нужного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a23b0-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="a23b0-108">На панели **Действия** справа в консоли конструктора CDC щелкните операцию, которую нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="a23b0-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="a23b0-109">Можно также щелкнуть имя экземпляра на левой панели и выбрать операцию, которую необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="a23b0-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="a23b0-110">Можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="a23b0-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="a23b0-111">**Запуск**. Запуск отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="a23b0-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="a23b0-112">**Остановка**. Остановка отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="a23b0-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="a23b0-113">**Сброс**. Щелкните **Сбросить** , чтобы сбросить экземпляр CDC до начального (пустого) состояния.</span><span class="sxs-lookup"><span data-stu-id="a23b0-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="a23b0-114">Этот параметр доступен только тогда, когда экземпляр CDC остановлен.</span><span class="sxs-lookup"><span data-stu-id="a23b0-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="a23b0-115">Все изменения в таблицах изменений, а также внутреннее состояние экземпляра CDC будут удалены.</span><span class="sxs-lookup"><span data-stu-id="a23b0-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="a23b0-116">При последующем запуске экземпляра CDC отслеживание изменений начнется с этого момента и будет содержать только те транзакции, выполнение которых началось после запуска экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a23b0-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="a23b0-117">**Удаление**. Удаление экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a23b0-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="a23b0-118">**Скрипт журналирования Oracle**. Щелкните **Скрипт журналирования Oracle** , чтобы открыть диалоговое окно со вспомогательным скриптом журналирования Oracle.</span><span class="sxs-lookup"><span data-stu-id="a23b0-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="a23b0-119">Сведения о том, что можно сделать в этом диалоговом окне, см. в разделе [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="a23b0-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="a23b0-120">**Примечание**. При выполнении скриптов дополнительного журналирования открывается диалоговое окно "Учетные данные Oracle для выполнения скриптов", в которое необходимо ввести допустимые имя пользователя Oracle и пароль.</span><span class="sxs-lookup"><span data-stu-id="a23b0-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="a23b0-121">Сведения об указании надлежащих учетных данных Oracle см. в разделе [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="a23b0-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="a23b0-122">**Развертывание экземпляра CDC**. Создание скрипта развертывания для экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a23b0-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="a23b0-123">Сведения об этом диалоговом окне см. в разделе [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="a23b0-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="a23b0-124">Дополнительные сведения об этих задачах см. в разделе [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="a23b0-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="a23b0-125">Можно также выбрать **Свойства** , чтобы изменить свойства конфигурации экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="a23b0-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="a23b0-126">Дополнительные сведения об изменении свойств экземпляра CDC см. в разделе [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a23b0-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
