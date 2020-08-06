---
title: Задача 9. Настройка службы ссылочных данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751543"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="dd272-102">Задача 9. Настройка службы эталонных данных</span><span class="sxs-lookup"><span data-stu-id="dd272-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="dd272-103">В этой задаче вы настраиваете DQS для использования службы ссылочных данных в Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dd272-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="dd272-104">В следующей задаче будет настроен домен **проверки адресов** для использования этой службы.</span><span class="sxs-lookup"><span data-stu-id="dd272-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="dd272-105">Во время выполнения операция очистки служб DQS передает значения доменов в домене **проверки адреса** службе для очистки.</span><span class="sxs-lookup"><span data-stu-id="dd272-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="dd272-106">Дополнительные сведения см. [в статье Настройка служб DQS для использования справочных данных](https://msdn.microsoft.com/library/hh213070.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dd272-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="dd272-107">На главной странице **клиента DQS**в области **Администрирование** щелкните **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="dd272-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="dd272-108">Убедитесь, что вкладка **Ссылочные данные** активна.</span><span class="sxs-lookup"><span data-stu-id="dd272-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="dd272-109">В области **Параметры сети** введите соответствующие значения в полях **прокси-сервер** и **порт** , если для подключения к Интернету необходимо использовать прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="dd272-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="dd272-110">Введите **ключ учетной записи Azure Marketplace** для поля **идентификатор учетной записи DataMarket** .</span><span class="sxs-lookup"><span data-stu-id="dd272-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="dd272-111">![Учетная запись службы эталонных данных Azure Data Market](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Учетная запись службы эталонных данных Azure Data Market")</span><span class="sxs-lookup"><span data-stu-id="dd272-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="dd272-112">Нажмите кнопку **проверить** рядом с текстовым полем, чтобы проверить идентификатор учетной записи.</span><span class="sxs-lookup"><span data-stu-id="dd272-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="dd272-113">Нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="dd272-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="dd272-114">Нажмите кнопку **Закрыть** в нижней части страницы, чтобы перейти на главную страницу клиента DQS.</span><span class="sxs-lookup"><span data-stu-id="dd272-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="dd272-115">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="dd272-115">Next Task</span></span>  
 [<span data-ttu-id="dd272-116">Задача 10. Настройка составного домена для использования службы эталонных данных</span><span class="sxs-lookup"><span data-stu-id="dd272-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
