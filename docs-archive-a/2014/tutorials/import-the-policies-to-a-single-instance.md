---
title: Импорт политик в один экземпляр | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740607"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="a80b5-102">Импорт политик в один экземпляр</span><span class="sxs-lookup"><span data-stu-id="a80b5-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="a80b5-103">При выполнении этой задачи будет осуществляться импорт рекомендованных политик в состав средств управления на основе политик на одном экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a80b5-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a80b5-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a80b5-104">Prerequisites</span></span>  
 <span data-ttu-id="a80b5-105">Эту процедуру необходимо выполнять на сервере, на котором запущен [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="a80b5-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="a80b5-106">Импорт рекомендованных политик для компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="a80b5-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="a80b5-107">Запустите среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]и подключитесь к компоненту [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a80b5-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a80b5-108">В обозревателе объектов последовательно разверните узлы **Управление**и **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="a80b5-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="a80b5-109">Щелкните правой кнопкой мыши **Политики**и выберите пункт **Импортировать политику**.</span><span class="sxs-lookup"><span data-stu-id="a80b5-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="a80b5-110">В диалоговом окне **Импорт** рядом с полем **импортируемые файлы** нажмите кнопку с многоточием (**...**).</span><span class="sxs-lookup"><span data-stu-id="a80b5-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="a80b5-111">В списке **Искать в** перейдите к следующей папке, которая содержит политики рекомендаций:</span><span class="sxs-lookup"><span data-stu-id="a80b5-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="a80b5-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="a80b5-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a80b5-113">Путь к файлу может меняться в зависимости от места установки файлов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , используемой версии (32-разрядной или 64-разрядной) операционной системы и идентификатора языка.</span><span class="sxs-lookup"><span data-stu-id="a80b5-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="a80b5-114">В диалоговом окне **Выбор политики** выберите один или несколько файлов политики.</span><span class="sxs-lookup"><span data-stu-id="a80b5-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="a80b5-115">Чтобы выбрать несмежные файлы, щелкните один файл, а затем, удерживая нажатой клавишу CTRL, выберите все необходимые дополнительные файлы.</span><span class="sxs-lookup"><span data-stu-id="a80b5-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="a80b5-116">Чтобы выбрать смежные файлы, щелкните первый файл, а затем, удерживая нажатой клавишу SHIFT, щелкните последний файл.</span><span class="sxs-lookup"><span data-stu-id="a80b5-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="a80b5-117">После завершения выбора файлов нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="a80b5-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="a80b5-118">В диалоговом окне **Импорт** убедитесь, что в списке **Состояние политики** установлено значение **Сохранить после импорта состояние политики** (значение по умолчанию), а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a80b5-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="a80b5-119">Политики импортируются в подузел **Политики** узла **Управление политиками**.</span><span class="sxs-lookup"><span data-stu-id="a80b5-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="a80b5-120">По умолчанию для импортированных политик задан режим выполнения «По запросу».</span><span class="sxs-lookup"><span data-stu-id="a80b5-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a80b5-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="a80b5-121">Next Steps</span></span>  
 [<span data-ttu-id="a80b5-122">Планирование политик</span><span class="sxs-lookup"><span data-stu-id="a80b5-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
