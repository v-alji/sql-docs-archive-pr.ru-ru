---
title: Экспорт сведений о зарегистрированном сервере
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737400"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="5f8c8-102">Выполнение экспорта сведений компонента «Зарегистрированные серверы» (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5f8c8-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5f8c8-103">В этом разделе описывается, как сохранить и экспортировать сведения о зарегистрированных серверах в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]и передать их другим сотрудникам и на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="5f8c8-104">Данную возможность экспорта можно использовать для создания согласованного пользовательского интерфейса на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="5f8c8-105">Экспорт и последующий импорт файлов зарегистрированных серверов позволяет легко настроить одинаковые серверы для нескольких компьютеров в окне «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="5f8c8-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="5f8c8-106">Это полезно при обращении к большому числу серверов с локальных компьютеров, расположенных в разных местах, или при необходимости настроить базовые параметры соединения для менее опытного пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f8c8-107">Регистрации серверов, использующих метод проверки подлинности SQL Server, хранят пароли индивидуально для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="5f8c8-108">После экспорта и импорта регистраций серверов пользователи при первом подключении должны ввести пароль для каждого сервера, после чего эти пароли сохраняются в списках зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="5f8c8-109">Вводить пароль необязательно для серверов, зарегистрированных с помощью проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="5f8c8-110">Экспорт сведений о зарегистрированных серверах</span><span class="sxs-lookup"><span data-stu-id="5f8c8-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="5f8c8-111">В окне "Зарегистрированные серверы" щелкните правой кнопкой мыши группу серверов и выберите пункт **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f8c8-112">Можно экспортировать отдельный сервер, все дерево зарегистрированных серверов или поддерево зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="5f8c8-113">В диалоговом окне **Экспорт зарегистрированных серверов** выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="5f8c8-114">**Группа серверов**</span><span class="sxs-lookup"><span data-stu-id="5f8c8-114">**Server group**</span></span>  
     <span data-ttu-id="5f8c8-115">Укажите группу серверов, которая будет экспортироваться.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="5f8c8-116">В файл экспорта можно экспортировать все зарегистрированные серверы, зарегистрированные серверы в определенной группе серверов, или какой-либо один зарегистрированный сервер.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="5f8c8-117">Операция экспорта является рекурсивной: если, например, группа серверов A содержит группу серверов B, а группа серверов B содержит группы серверов C и D, в ходе экспорта группы серверов A будут экспортированы все записи из A, B, C и D.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="5f8c8-118">Группа серверов отображает только группы серверов из дерева текущего зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="5f8c8-119">**Файл экспорта**</span><span class="sxs-lookup"><span data-stu-id="5f8c8-119">**Export file**</span></span>  
     <span data-ttu-id="5f8c8-120">Введите в текстовом поле имя файла экспорта или нажмите кнопку обзора ( **...** ), чтобы найти файл экспорта на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="5f8c8-121">Если выбрать существующий файл, то сведения о зарегистрированном сервере добавятся в этот файл.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="5f8c8-122">Используйте расширение REGSRVR.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="5f8c8-123">Чтобы сведения о зарегистрированном сервере стали доступны другим пользователям или другому компьютеру, можно сохранить файл в сети.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="5f8c8-124">Другие пользователи смогут получить доступ к файлу и выполнить импорт части или всех сведений о зарегистрированных серверах.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="5f8c8-125">Если выбрать существующий файл в качестве файла для экспорта, то содержимое файла будет перезаписано сведениями о зарегистрированных серверах.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="5f8c8-126">**Не включать в экспортируемые файлы имена пользователей и пароли**</span><span class="sxs-lookup"><span data-stu-id="5f8c8-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="5f8c8-127">Имена пользователей исключаются из данных, экспортируемых в файл.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5f8c8-128">Хотя файлы экспорта зашифрованы, необходимо тщательно контролировать доступ к ним в случае, если в них заносятся имена пользователей и пароли для процедуры проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="5f8c8-129">Поэтому по умолчанию из файла экспорта исключаются имена пользователей и пароли.</span><span class="sxs-lookup"><span data-stu-id="5f8c8-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8c8-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f8c8-130">See Also</span></span>  
 <span data-ttu-id="5f8c8-131">[Импортировать сведения о зарегистрированном сервере &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [создать новый зарегистрированный сервер &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="5f8c8-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
