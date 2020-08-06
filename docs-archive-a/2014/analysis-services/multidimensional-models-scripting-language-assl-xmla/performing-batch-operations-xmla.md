---
title: Выполнение пакетных операций (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- multiple projects
- XML for Analysis, batches
- parallel batch execution [XMLA]
- transactional batches
- serial batch execution [XMLA]
- XMLA, batches
- batches [XML for Analysis]
- nontransactional batches
ms.assetid: 731c70e5-ed51-46de-bb69-cbf5aea18dda
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69899077cf534482879accbf10640f6295e3866a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656026"
---
# <a name="performing-batch-operations-xmla"></a><span data-ttu-id="55d8d-102">Выполнение пакетных операций (XMLA)</span><span class="sxs-lookup"><span data-stu-id="55d8d-102">Performing Batch Operations (XMLA)</span></span>
  <span data-ttu-id="55d8d-103">Команду [Batch](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) можно использовать в XML для АНАЛИТИКИ (XMLA) для выполнения нескольких команд XMLA с помощью одного метода [EXECUTE](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) XMLA.</span><span class="sxs-lookup"><span data-stu-id="55d8d-103">You can use the [Batch](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) command in XML for Analysis (XMLA) to run multiple XMLA commands using a single XMLA [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span> <span data-ttu-id="55d8d-104">Несколько команд, содержащихся в команде `Batch`, можно выполнить либо как одну транзакцию, либо как отдельные транзакции для каждой команды, последовательно или параллельно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-104">You can run multiple commands contained in the `Batch` command either as a single transaction or in individual transactions for each command, in serial or in parallel.</span></span> <span data-ttu-id="55d8d-105">Для обработки нескольких объектов можно также указать нелинейные привязки и другие свойства в `Batch` команде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55d8d-105">You can also specify out-of-line bindings and other properties in the `Batch` command for processing multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
## <a name="running-transactional-and-nontransactional-batch-commands"></a><span data-ttu-id="55d8d-106">Выполнение транзакционных и нетранзакционных пакетных команд</span><span class="sxs-lookup"><span data-stu-id="55d8d-106">Running Transactional and Nontransactional Batch Commands</span></span>  
 <span data-ttu-id="55d8d-107">Команда `Batch` выполняет команды одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="55d8d-107">The `Batch` command executes commands in one of two ways:</span></span>  
  
 <span data-ttu-id="55d8d-108">**Транзакционная**</span><span class="sxs-lookup"><span data-stu-id="55d8d-108">**Transactional**</span></span>  
 <span data-ttu-id="55d8d-109">Если `Transaction` `Batch` для атрибута команды задано значение true, `Batch` команда выполняет команды, содержащиеся `Batch` в команде, в одной транзакции — *транзакционном* пакете.</span><span class="sxs-lookup"><span data-stu-id="55d8d-109">If the `Transaction` attribute of the `Batch` command is set to true, the `Batch` command run commands all of the commands contained by the `Batch` command in a single transaction-a *transactional* batch.</span></span>  
  
 <span data-ttu-id="55d8d-110">Если какая-либо команда завершается ошибкой в транзакционном пакете, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] выполняет откат любой команды в `Batch` команде, которая выполнялась до сбоя команды, и `Batch` команда немедленно завершается.</span><span class="sxs-lookup"><span data-stu-id="55d8d-110">If any command fails in a transactional batch, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] rolls back any command in the `Batch` command that ran before the command that failed and the `Batch` command immediately ends.</span></span> <span data-ttu-id="55d8d-111">Все команды, содержащиеся в команде `Batch`, которые еще не запускались, выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="55d8d-111">Any commands in the `Batch` command that have not yet run are not executed.</span></span> <span data-ttu-id="55d8d-112">После завершения команды `Batch` команда `Batch` сообщает обо всех ошибках, возникших при выполнении команды, завершившейся неудачей.</span><span class="sxs-lookup"><span data-stu-id="55d8d-112">After the `Batch` command ends, the `Batch` command reports any errors that occurred for the failed command.</span></span>  
  
 <span data-ttu-id="55d8d-113">**Нетранзакционные**</span><span class="sxs-lookup"><span data-stu-id="55d8d-113">**Nontransactional**</span></span>  
 <span data-ttu-id="55d8d-114">Если `Transaction` атрибут имеет значение false, `Batch` команда выполняет каждую команду, содержащуюся `Batch` в команде, в отдельную транзакцию — *нетранзакционный* пакет.</span><span class="sxs-lookup"><span data-stu-id="55d8d-114">If the `Transaction` attribute is set to false, the `Batch` command runs each command contained by the `Batch` command in a separate transaction-a *nontransactional* batch.</span></span> <span data-ttu-id="55d8d-115">Если в нетранзакционном пакете одна из команд завершается ошибкой, команда `Batch` продолжает выполнение команд после той команды, которая завершилась неудачей.</span><span class="sxs-lookup"><span data-stu-id="55d8d-115">If any command fails in a nontransactional batch, the `Batch` command continues to run commands after the command which failed.</span></span> <span data-ttu-id="55d8d-116">После того как команда `Batch` предпримет попытки выполнить все команды, содержащиеся в команде `Batch`, то команда `Batch` сообщит обо всех возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="55d8d-116">After the `Batch` command tries to run all the commands that the `Batch` command contains, the `Batch` command reports any errors that occurred.</span></span>  
  
 <span data-ttu-id="55d8d-117">Все результаты, возвращаемые командами, которые содержатся в команде `Batch`, возвращаются в том порядке, в котором эти команды расположены в команде `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-117">All results returned by commands contained in a `Batch` command are returned in the same order in which the commands are contained in the `Batch` command.</span></span> <span data-ttu-id="55d8d-118">В зависимости от того, является ли команда `Batch` транзакционной или нетранзакционной, команда `Batch` возвращает разные результаты.</span><span class="sxs-lookup"><span data-stu-id="55d8d-118">The results returned by a `Batch` command vary based on whether the `Batch` command is transactional or nontransactional.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55d8d-119">Если `Batch` команда содержит команду, которая не возвращает выходные данные, например команду [Lock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) , и эта команда успешно выполняется, `Batch` команда возвращает пустой [корневой](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) элемент в элементе Results.</span><span class="sxs-lookup"><span data-stu-id="55d8d-119">If a `Batch` command contains a command that does not return output, such as the [Lock](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/lock-element-xmla) command, and that command successfully runs, the `Batch` command returns an empty [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element within the results element.</span></span> <span data-ttu-id="55d8d-120">Пустой элемент `root` дает возможность сопоставить каждую команду, содержащуюся в команде `Batch`, с соответствующим элементом `root` для результатов этой команды.</span><span class="sxs-lookup"><span data-stu-id="55d8d-120">The empty `root` element ensures that each command contained in a `Batch` command can be matched with the appropriate `root` element for that command's results.</span></span>  
  
### <a name="returning-results-from-transactional-batch-results"></a><span data-ttu-id="55d8d-121">Возвращение результатов из результатов транзакционного пакета</span><span class="sxs-lookup"><span data-stu-id="55d8d-121">Returning Results from Transactional Batch Results</span></span>  
 <span data-ttu-id="55d8d-122">Результаты команд, выполняющихся в рамках транзакционного пакета, возвращаются только после завершения выполнения всей команды `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-122">Results from commands run within a transactional batch are not returned until the entire `Batch` command is completed.</span></span> <span data-ttu-id="55d8d-123">Результаты каждой команды не возвращаются отдельно по мере их выполнения, поскольку завершение с ошибкой любой команды в рамках транзакционного пакета приводит к откату всей команды `Batch` и всех содержащихся в ней команд.</span><span class="sxs-lookup"><span data-stu-id="55d8d-123">The results are not returned after each command runs because any command that fails within a transactional batch would cause the entire `Batch` command and all containing commands to be rolled back.</span></span> <span data-ttu-id="55d8d-124">Если все команды запускаются и выполняются успешно, элемент [return](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/return-element-xmla) элемента [ExecuteResponse](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects-executeresponse) , возвращаемый `Execute` методом для `Batch` команды, содержит один элемент [Results](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/results-element-xmla) , который, в свою очередь, содержит один `root` элемент для каждой успешно выполненной команды, содержащейся в `Batch` команде.</span><span class="sxs-lookup"><span data-stu-id="55d8d-124">If all commands start and run successfully, the [return](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/return-element-xmla) element of the [ExecuteResponse](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects-executeresponse) element returned by the `Execute` method for the `Batch` command contains one [results](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/results-element-xmla) element, which in turn contains one `root` element for each successfully run command contained in the `Batch` command.</span></span> <span data-ttu-id="55d8d-125">Если же одну из команд в команде `Batch` не удалось запустить или она завершилась ошибкой, метод `Execute` возвращает сбой SOAP для команды `Batch`, в котором содержится ошибка команды, завершившейся неудачей.</span><span class="sxs-lookup"><span data-stu-id="55d8d-125">If any command in the `Batch` command cannot be started or fails to complete, the `Execute` method returns a SOAP fault for the `Batch` command that contains the error of the command that failed.</span></span>  
  
### <a name="returning-results-from-nontransactional-batch-results"></a><span data-ttu-id="55d8d-126">Возвращение результатов из результатов нетранзакционного пакета</span><span class="sxs-lookup"><span data-stu-id="55d8d-126">Returning Results from Nontransactional Batch Results</span></span>  
 <span data-ttu-id="55d8d-127">Результаты выполнения команд в рамках нетранзакционного пакета возвращаются в том порядке, в котором эти команды расположены в команде `Batch` и с учетом их возврата каждой командой.</span><span class="sxs-lookup"><span data-stu-id="55d8d-127">Results from commands run within a nontransactional batch are returned in the order in which the commands are contained within the `Batch` command and as they are returned by each command.</span></span> <span data-ttu-id="55d8d-128">Если не удалось запустить ни одной команды, содержащейся в команде `Batch`, метод `Execute` возвращает сбой SOAP, который содержит ошибку для команды `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-128">If no command contained in the `Batch` command can be successfully started, the `Execute` method returns a SOAP fault that contains an error for the `Batch` command.</span></span> <span data-ttu-id="55d8d-129">Если удалось запустить хотя бы одну команду, элемент `return` элемента `ExecuteResponse`, возвращаемого методом `Execute` для команды `Batch`, будет содержать один элемент `results`, в котором, в свою очередь, будет содержаться по одному элементу `root` для каждой команды, находящейся в команде `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-129">If at least one command is successfully started, the `return` element of the `ExecuteResponse` element returned by the `Execute` method for the `Batch` command contains one `results` element, which in turn contains one `root` element for each command contained in the `Batch` command.</span></span> <span data-ttu-id="55d8d-130">Если одна или несколько команд в нетранзакционном пакете не могут быть запущены или завершаться неудачей, `root` элемент для этой невыполненной команды содержит элемент [Error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) , описывающий ошибку.</span><span class="sxs-lookup"><span data-stu-id="55d8d-130">If one or more commands in a nontransactional batch cannot be started or fails to complete, the `root` element for that failed command contains an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) element describing the error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55d8d-131">Считается, что нетранзакционный пакет выполнен успешно, если из него удалось запустить хотя бы одну команду, даже если все команды, содержащиеся в таком пакете, возвратят ошибку в результатах выполнения команды `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-131">As long as at least one command in a nontransactional batch can be started, the nontransactional batch is considered to have successfully run, even if every command contained in the nontransactional batch returns an error in the results of the `Batch` command.</span></span>  
  
## <a name="using-serial-and-parallel-execution"></a><span data-ttu-id="55d8d-132">Использование последовательного и параллельного выполнения</span><span class="sxs-lookup"><span data-stu-id="55d8d-132">Using Serial and Parallel Execution</span></span>  
 <span data-ttu-id="55d8d-133">Команду `Batch` можно использовать для последовательного или параллельного выполнения включенных в нее команд.</span><span class="sxs-lookup"><span data-stu-id="55d8d-133">You can use the `Batch` command to run included commands in serial or in parallel.</span></span> <span data-ttu-id="55d8d-134">При последовательном выполнении следующая команда из команды `Batch` может запуститься только после завершения выполнения текущей команды в команде `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-134">When the commands are run in serial, the next command included in the `Batch` command cannot start until the currently running command in the `Batch` command is completed.</span></span> <span data-ttu-id="55d8d-135">При параллельном выполнении команд команда `Batch` может выполнять несколько команд одновременно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-135">When the commands are run in parallel, multiple commands can be executed simultaneously by the `Batch` command.</span></span>  
  
 <span data-ttu-id="55d8d-136">Для параллельного выполнения команд необходимо добавить команды, которые будут выполняться параллельно, в свойство [Parallel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/parallel-element-xmla) `Batch` команды.</span><span class="sxs-lookup"><span data-stu-id="55d8d-136">To run commands in parallel, you add the commands to be run in parallel to the [Parallel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/parallel-element-xmla) property of the `Batch` command.</span></span> <span data-ttu-id="55d8d-137">В настоящее время [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в параллельном режиме могут выполняться только последовательные последовательные командные [процессы](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="55d8d-137">Currently, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] can run only contiguous, sequential [Process](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) commands in parallel.</span></span> <span data-ttu-id="55d8d-138">Любая другая команда XMLA, например [CREATE](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) или [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla), включенная в свойство, выполняется `Parallel` последовательно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-138">Any other XMLA command, such as [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) or [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla), included in the `Parallel` property is run serially.</span></span>  
  
 <span data-ttu-id="55d8d-139">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] пытаются выполнить все команды `Process`, включенные в свойство `Parallel`, в параллельном режиме, однако гарантировать параллельное выполнение всех команд `Process` невозможно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-139">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tries to run all `Process` commands included in the `Parallel` property in parallel, but cannot guarantee that all included `Process` commands can be run in parallel.</span></span> <span data-ttu-id="55d8d-140">Экземпляр анализирует каждую команду `Process`, а если обнаруживается, что выполнить команду в параллельном режиме невозможно, выполняет команду `Process` последовательно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-140">The instance analyzes each `Process` command and, if the instance determines that the command cannot be run in parallel, the `Process` command is run in serial.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55d8d-141">Чтобы команды можно было выполнять параллельно, атрибуту `Transaction` команды `Batch` необходимо присвоить значение TRUE, так как службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] поддерживают только одну активную транзакцию на соединение, а нетранзакционные пакеты выполняют каждую команду в отдельной транзакции.</span><span class="sxs-lookup"><span data-stu-id="55d8d-141">To run commands in parallel, the `Transaction` attribute of the `Batch` command must be set to true because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports only one active transaction per connection and nontransactional batches run each command in a separate transaction.</span></span> <span data-ttu-id="55d8d-142">В случае включения свойства `Parallel` в нетранзакционный пакет возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="55d8d-142">If you include the `Parallel` property in a nontransactional batch, an error occurs.</span></span>  
  
### <a name="limiting-parallel-execution"></a><span data-ttu-id="55d8d-143">Ограничение параллельного выполнения</span><span class="sxs-lookup"><span data-stu-id="55d8d-143">Limiting Parallel Execution</span></span>  
 <span data-ttu-id="55d8d-144">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] пытаются выполнить как можно большее число команд `Process` параллельно, с учетом возможностей компьютера, на котором работает экземпляр служб.</span><span class="sxs-lookup"><span data-stu-id="55d8d-144">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance tries to run as many `Process` commands in parallel as possible, up to the limits of the computer on which the instance runs.</span></span> <span data-ttu-id="55d8d-145">Можно ограничить число одновременно выполняющихся команд `Process`, присвоив атрибуту `maxParallel` свойства `Parallel` значение, указывающее максимальное число команд `Process`, которые могут выполняться параллельно.</span><span class="sxs-lookup"><span data-stu-id="55d8d-145">You can limit the number of concurrently executing `Process` commands by setting the `maxParallel` attribute of the `Parallel` property to a value indicating the maximum number of `Process` commands that can be run in parallel.</span></span>  
  
 <span data-ttu-id="55d8d-146">Например, в приведенной последовательности свойство `Parallel` содержит следующие команды:</span><span class="sxs-lookup"><span data-stu-id="55d8d-146">For example, a `Parallel` property contains the following commands in the sequence listed:</span></span>  
  
1.  `Create`  
  
2.  `Process`  
  
3.  `Alter`  
  
4.  `Process`  
  
5.  `Process`  
  
6.  `Process`  
  
7.  `Delete`  
  
8.  `Process`  
  
9. `Process`  
  
 <span data-ttu-id="55d8d-147">Атрибут `maxParalle` этого свойства `Parallel` имеет значение 2.</span><span class="sxs-lookup"><span data-stu-id="55d8d-147">The `maxParalle`l attribute of this `Parallel` property is set to 2.</span></span> <span data-ttu-id="55d8d-148">Это означает, что экземпляр выполнит приведенный ранее список команд в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="55d8d-148">Therefore, the instance runs the previous lists of commands as described in the following list:</span></span>  
  
-   <span data-ttu-id="55d8d-149">Команда 1 будет выполнена последовательно, так как это команда `Create`, а параллельно могут выполняться только команды `Process`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-149">Command 1 runs serially because command 1 is a `Create` command and only `Process` commands can be run in parallel.</span></span>  
  
-   <span data-ttu-id="55d8d-150">Команда 2 выполняется последовательно после завершения выполнения команды 1.</span><span class="sxs-lookup"><span data-stu-id="55d8d-150">Command 2 runs serially after command 1 is completed.</span></span>  
  
-   <span data-ttu-id="55d8d-151">Команда 3 выполняется последовательно после завершения выполнения команды 2.</span><span class="sxs-lookup"><span data-stu-id="55d8d-151">Command 3 runs serially after command 2 is completed.</span></span>  
  
-   <span data-ttu-id="55d8d-152">Команды 4 и 5 выполняются параллельно после завершения выполнения команды 3.</span><span class="sxs-lookup"><span data-stu-id="55d8d-152">Commands 4 and 5 run in parallel after command 3 is completed.</span></span> <span data-ttu-id="55d8d-153">Несмотря на то, что команда 6 также является командой `Process`, она не может выполняться параллельно с командами 4 и 5, поскольку свойство `maxParallel` имеет значение 2.</span><span class="sxs-lookup"><span data-stu-id="55d8d-153">Although command 6 is also a `Process` command, command 6 cannot run in parallel with commands 4 and 5 because the `maxParallel` property is set to 2.</span></span>  
  
-   <span data-ttu-id="55d8d-154">Команда будет выполнена последовательно после завершения команд 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="55d8d-154">Command 6 runs serially after both commands 4 and 5 are completed.</span></span>  
  
-   <span data-ttu-id="55d8d-155">Команда 7 выполняется последовательно за командой 6.</span><span class="sxs-lookup"><span data-stu-id="55d8d-155">Command 7 runs serially after command 6 is completed.</span></span>  
  
-   <span data-ttu-id="55d8d-156">Команды 8 и 9 выполняются параллельно после завершения команды 7.</span><span class="sxs-lookup"><span data-stu-id="55d8d-156">Commands 8 and 9 run in parallel after command 7 is completed.</span></span>  
  
## <a name="using-the-batch-command-to-process-objects"></a><span data-ttu-id="55d8d-157">Использование пакетов команд для обработки объектов</span><span class="sxs-lookup"><span data-stu-id="55d8d-157">Using the Batch Command to Process Objects</span></span>  
 <span data-ttu-id="55d8d-158">Команда `Batch` содержит несколько дополнительных свойств и атрибутов, включенных в нее специально для поддержки обработки нескольких проектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d8d-158">The `Batch` command contains several optional properties and attributes specifically included to support processing multiple [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects:</span></span>  
  
-   <span data-ttu-id="55d8d-159">Атрибут `ProcessAffectedObjects` команды `Batch` указывает, должен ли экземпляр обрабатывать также любые объекты, которым в результате команды `Process`, включенной в команду `Batch`, обрабатывающую указанный объект, требуется повторная обработка.</span><span class="sxs-lookup"><span data-stu-id="55d8d-159">The `ProcessAffectedObjects` attribute of the `Batch` command indicates whether the instance should also process any object that requires reprocessing as a result of a `Process` command included in the `Batch` command processing a specified object.</span></span>  
  
-   <span data-ttu-id="55d8d-160">Свойство [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla) содержит коллекцию нелинейных привязок, используемых всеми `Process` командами в `Batch` команде.</span><span class="sxs-lookup"><span data-stu-id="55d8d-160">The [Bindings](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/bindings-element-xmla) property contains a collection of out-of-line bindings used by all of the `Process` commands in the `Batch` command.</span></span>  
  
-   <span data-ttu-id="55d8d-161">Свойство [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) содержит нелинейную привязку для источника данных, используемого всеми `Process` командами в `Batch` команде.</span><span class="sxs-lookup"><span data-stu-id="55d8d-161">The [DataSource](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property contains an out-of-line binding for a data source used by all of the `Process` commands in the `Batch` command.</span></span>  
  
-   <span data-ttu-id="55d8d-162">Свойство [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) содержит нелинейную привязку для представления источника данных, используемого всеми `Process` командами в `Batch` команде.</span><span class="sxs-lookup"><span data-stu-id="55d8d-162">The [DataSourceView](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/datasourceview-element-xmla) property contains an out-of-line binding for a data source view used by all of the `Process` commands in the `Batch` command.</span></span>  
  
-   <span data-ttu-id="55d8d-163">Свойство [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) указывает способ, с помощью которого `Batch` команда обрабатывает ошибки, обнаруженные всеми `Process` командами, содержащимися в `Batch` команде.</span><span class="sxs-lookup"><span data-stu-id="55d8d-163">The [ErrorConfiguration](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/errorconfiguration-element-xmla) property specifies the way in which the `Batch` command handles errors encountered by all `Process` commands contained in the `Batch` command.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="55d8d-164">Команда `Process` не может содержать свойств `Bindings`, `DataSource`, `DataSourceView`, `ErrorConfiguration` или `Process`, если она находится в команде `Batch`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-164">A `Process` command cannot include the `Bindings`, `DataSource`, `DataSourceView`, or `ErrorConfiguration` properties, if the `Process` command is contained in a `Batch` command.</span></span> <span data-ttu-id="55d8d-165">Если эти свойства для команды `Process` задать необходимо, укажите требуемые сведения в соответствующих свойствах команды `Batch`, которая содержит команду `Process`.</span><span class="sxs-lookup"><span data-stu-id="55d8d-165">If you must specify these properties for a `Process` command, provide the necessary information in the corresponding properties of the `Batch` command that contains the `Process` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d8d-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="55d8d-166">See Also</span></span>  
 <span data-ttu-id="55d8d-167">[Пакетный элемент &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="55d8d-167">[Batch Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/batch-element-xmla) </span></span>  
 <span data-ttu-id="55d8d-168">[Элемент Process &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="55d8d-168">[Process Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/process-element-xmla) </span></span>  
 <span data-ttu-id="55d8d-169">[Обработка объектов многомерной модели](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="55d8d-169">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 [<span data-ttu-id="55d8d-170">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="55d8d-170">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  