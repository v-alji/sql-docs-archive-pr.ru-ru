---
title: 'Средство управления командной строки: SqlLocalDB.exe | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655741"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="f48ef-102">Программа командной строки: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="f48ef-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="f48ef-103">Программа SqlLocalDB.exe — это простое средство для управления экземплярами LocalDB из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f48ef-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="f48ef-104">Оно реализовано как простая оболочка для API экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f48ef-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="f48ef-105">Как и во многих аналогичных средствах SQL Server (например, SQLCMD), параметры передаются в SqlLocalDB как параметры командной строки, а вывод отправляется на консоль.</span><span class="sxs-lookup"><span data-stu-id="f48ef-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="f48ef-106">Программа SqlLocalDB позволяет разработчикам использовать LocalDB без необходимости писать код для вызова API или использования других средств для этой цели.</span><span class="sxs-lookup"><span data-stu-id="f48ef-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="f48ef-107">Параметры программы SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="f48ef-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="f48ef-108">SqlLocalDB поддерживает следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f48ef-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="f48ef-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="f48ef-109">Option</span></span>|<span data-ttu-id="f48ef-110">Действие</span><span class="sxs-lookup"><span data-stu-id="f48ef-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="f48ef-111">Выводит текст справки.</span><span class="sxs-lookup"><span data-stu-id="f48ef-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="f48ef-112">Создает новый экземпляр LocalDB с заданным именем и версией.</span><span class="sxs-lookup"><span data-stu-id="f48ef-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="f48ef-113">Если параметр [version-number] опущен, используется значение по умолчанию — версия сборки SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="f48ef-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="f48ef-114">-s запускает новый экземпляр LocalDB после его создания.</span><span class="sxs-lookup"><span data-stu-id="f48ef-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="f48ef-115">Удаляет экземпляр LocalDB с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="f48ef-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="f48ef-116">Запускает экземпляр LocalDB с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="f48ef-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="f48ef-117">Останавливает экземпляр LocalDB с заданным именем после завершения выполнения текущих запросов.</span><span class="sxs-lookup"><span data-stu-id="f48ef-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="f48ef-118">-i запрашивает завершение работы экземпляра LocalDB с параметром NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="f48ef-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="f48ef-119">-k прерывает процесс экземпляра LocalDB, не связываясь с ним.</span><span class="sxs-lookup"><span data-stu-id="f48ef-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="f48ef-120">Делает указанный частный экземпляр общим, используя указанное общее имя.</span><span class="sxs-lookup"><span data-stu-id="f48ef-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="f48ef-121">Если идентификатор безопасности пользователя или имя учетной записи не указаны, используется значение по умолчанию — имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="f48ef-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="f48ef-122">Выводит из совместного использования указанный общий экземпляр LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f48ef-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="f48ef-123">Перечисляет все существующие экземпляры LocalDB, принадлежащие текущему пользователю, и все общие экземпляры LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f48ef-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="f48ef-124">Выводит сведения об указанном экземпляре LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f48ef-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="f48ef-125">Перечисляет все версии LocalDB, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f48ef-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="f48ef-126">Включает или отключает трассировку.</span><span class="sxs-lookup"><span data-stu-id="f48ef-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="f48ef-127">Программа SqlLocalDB рассматривает пробелы как разделители; имена экземпляров, которые содержат пробелы и специальные символы, необходимо заключать в кавычки.</span><span class="sxs-lookup"><span data-stu-id="f48ef-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="f48ef-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="f48ef-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
