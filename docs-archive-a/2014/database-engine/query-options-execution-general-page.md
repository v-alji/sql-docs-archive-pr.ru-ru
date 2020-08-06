---
title: Выполнение параметров запроса (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667387"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="6d93f-102">Выполнение параметров запроса (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="6d93f-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="6d93f-103">Используйте эту страницу, чтобы задать параметры для запросов служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d93f-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="6d93f-104">Для доступа к этому диалоговому окну щелкните правой кнопкой мыши тело окна "Редактор запросов", а затем щелкните **Параметры запроса**.</span><span class="sxs-lookup"><span data-stu-id="6d93f-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6d93f-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="6d93f-105">UI element list</span></span>  
 <span data-ttu-id="6d93f-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="6d93f-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="6d93f-107">Значение по умолчанию, равное 0, указывает на то, что [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] будет продолжать ожидание результатов, пока все из них не будут получены.</span><span class="sxs-lookup"><span data-stu-id="6d93f-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="6d93f-108">При установке значения больше 0 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] прервет запрос после получения указанного числа строк.</span><span class="sxs-lookup"><span data-stu-id="6d93f-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="6d93f-109">Для выключения этого параметра (чтобы возвращались все строки) задайте SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="6d93f-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="6d93f-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="6d93f-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="6d93f-111">Значение по умолчанию, равное 2 147 483 647 байт, указывает на то, что [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] предоставит содержимое поля полностью, вплоть до пределов для полей данных `text`, `ntext`, `nvarchar(max)` и `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="6d93f-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="6d93f-112">Этот параметр не влияет на тип данных xml.</span><span class="sxs-lookup"><span data-stu-id="6d93f-112">It does not affect the XML data type.</span></span> <span data-ttu-id="6d93f-113">Задав меньшее число, можно ограничить вывод результатов в случае больших значений.</span><span class="sxs-lookup"><span data-stu-id="6d93f-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="6d93f-114">Содержимое столбцов большего размера, чем заданное число, будет усекаться.</span><span class="sxs-lookup"><span data-stu-id="6d93f-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="6d93f-115">**Время ожидания выполнения**</span><span class="sxs-lookup"><span data-stu-id="6d93f-115">**Execution time-out**</span></span>  
 <span data-ttu-id="6d93f-116">Указывает число секунд ожидания перед отменой запроса.</span><span class="sxs-lookup"><span data-stu-id="6d93f-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="6d93f-117">Значение, равное 0, указывает на неограниченное время ожидания или отсутствие времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="6d93f-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="6d93f-118">**Разделитель пакетов**</span><span class="sxs-lookup"><span data-stu-id="6d93f-118">**Batch separator**</span></span>  
 <span data-ttu-id="6d93f-119">Введите слово, которое будет использоваться для разделения инструкций Transact-SQL на пакеты.</span><span class="sxs-lookup"><span data-stu-id="6d93f-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="6d93f-120">Значение по умолчанию — GO.</span><span class="sxs-lookup"><span data-stu-id="6d93f-120">The default is GO.</span></span>  
  
 <span data-ttu-id="6d93f-121">**По умолчанию открывать новые запросы в режиме SQLCMD**</span><span class="sxs-lookup"><span data-stu-id="6d93f-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="6d93f-122">При установке этого флажка новые запросы будут открываться в режиме SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="6d93f-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="6d93f-123">Этот флажок отображается только в том случае, если диалоговое окно открыто из меню " **Сервис** ".</span><span class="sxs-lookup"><span data-stu-id="6d93f-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="6d93f-124">При выборе этого параметра следует учитывать следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="6d93f-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="6d93f-125">Технология IntelliSense в редакторе запросов компонента [!INCLUDE[ssDE](../includes/ssde-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="6d93f-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="6d93f-126">Поскольку редактор запросов не запускается из командной строки, невозможно передать ему такие параметры командной строки, как переменные.</span><span class="sxs-lookup"><span data-stu-id="6d93f-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="6d93f-127">Поскольку редактор запросов не может ответить на подсказки и приглашения операционной системы, будьте внимательны и не запускайте интерактивные инструкции.</span><span class="sxs-lookup"><span data-stu-id="6d93f-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="6d93f-128">**По умолчанию**</span><span class="sxs-lookup"><span data-stu-id="6d93f-128">**Reset to Default**</span></span>  
 <span data-ttu-id="6d93f-129">Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.</span><span class="sxs-lookup"><span data-stu-id="6d93f-129">Resets all values on this page to the original default values.</span></span>  
  
  
