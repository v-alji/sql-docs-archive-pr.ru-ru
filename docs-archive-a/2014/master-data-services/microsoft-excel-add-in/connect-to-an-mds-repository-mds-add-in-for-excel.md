---
title: Соединение с репозиторием MDS (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730794"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="cbc11-102">Соединение с репозиторием MDS (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="cbc11-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="cbc11-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]необходимо установить соединение с репозиторием MDS, прежде чем можно будет загружать или публиковать данные.</span><span class="sxs-lookup"><span data-stu-id="cbc11-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cbc11-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cbc11-104">Prerequisites</span></span>  
 <span data-ttu-id="cbc11-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="cbc11-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="cbc11-106">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="cbc11-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="cbc11-107">Соединение с репозиторием MDS</span><span class="sxs-lookup"><span data-stu-id="cbc11-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="cbc11-108">В MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]на вкладке **Основные данные** в группе **Соединение и загрузка** нажмите стрелку под кнопкой **Соединение** и выберите команду **Управление соединениями**.</span><span class="sxs-lookup"><span data-stu-id="cbc11-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="cbc11-109">В диалоговом окне **Управление соединениями** в разделе **Новое соединение** нажмите кнопку **Создать новое соединение**.</span><span class="sxs-lookup"><span data-stu-id="cbc11-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="cbc11-110">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="cbc11-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="cbc11-111">В диалоговом окне **Добавление нового соединения** в поле **Описание** введите описание соединения.</span><span class="sxs-lookup"><span data-stu-id="cbc11-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="cbc11-112">Это соединение будет отображаться при нажатии стрелки кнопки **Соединение** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="cbc11-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="cbc11-113">В поле **Адрес сервера MDS** введите URL-адрес веб-приложения [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], например http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="cbc11-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cbc11-114">Следует использовать имя компьютера, а не localhost.</span><span class="sxs-lookup"><span data-stu-id="cbc11-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="cbc11-115">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cbc11-115">Click **OK**.</span></span> <span data-ttu-id="cbc11-116">Это имя появится в разделе **Существующие соединения** .</span><span class="sxs-lookup"><span data-stu-id="cbc11-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="cbc11-117">Можно нажать кнопку **Проверка** , чтобы проверить соединение.</span><span class="sxs-lookup"><span data-stu-id="cbc11-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="cbc11-118">Будет выдано диалоговое окно подтверждения или сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cbc11-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="cbc11-119">Чтобы закрыть его, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="cbc11-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="cbc11-120">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="cbc11-120">Click **Connect**.</span></span> <span data-ttu-id="cbc11-121">Отображается панель **Службы Master Data Services** .</span><span class="sxs-lookup"><span data-stu-id="cbc11-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cbc11-122">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cbc11-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="cbc11-123">Загрузка данных из MDS в Excel</span><span class="sxs-lookup"><span data-stu-id="cbc11-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="cbc11-124">Фильтровать данные перед загрузкой &#40;надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="cbc11-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="cbc11-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbc11-125">See Also</span></span>  
 [<span data-ttu-id="cbc11-126">Соединения (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="cbc11-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
