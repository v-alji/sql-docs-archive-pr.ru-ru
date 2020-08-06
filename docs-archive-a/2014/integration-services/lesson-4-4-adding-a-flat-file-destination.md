---
title: Шаг 4. Добавление назначения "Неструктурированный файл" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735470"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="6b152-102">Шаг 4. Добавление назначения «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="6b152-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="6b152-103">Выход ошибок преобразования «Ключ уточняющего запроса валют» перенаправляет в преобразование «Скрипт» все строки данных, завершившиеся ошибкой в операции поиска.</span><span class="sxs-lookup"><span data-stu-id="6b152-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="6b152-104">Для расширения сведений о возникших ошибках преобразование «Скрипт» выполняет скрипт, получающий описания ошибок.</span><span class="sxs-lookup"><span data-stu-id="6b152-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="6b152-105">В этой задаче все сведения об ошибках строк будут сохранены для последующей обработки в файле с разделителями.</span><span class="sxs-lookup"><span data-stu-id="6b152-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="6b152-106">Чтобы сохранить ошибочные строки, необходимо добавить и настроить диспетчер соединений с неструктурированными файлами для текстового файла, который будет содержать данные об ошибках, и назначение «Неструктурированный файл».</span><span class="sxs-lookup"><span data-stu-id="6b152-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="6b152-107">Путем установки свойств в диспетчере соединений с неструктурированными файлами, который использует назначение «Неструктурированный файл», можно определить способ, которым назначение «Неструктурированный файл» форматирует и записывает текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="6b152-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="6b152-108">Дополнительные сведения см. в разделе [Диспетчер соединений](connection-manager/file-connection-manager.md) с неструктурированными файлами и [Назначение «Неструктурированный файл](data-flow/flat-file-destination.md)».</span><span class="sxs-lookup"><span data-stu-id="6b152-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="6b152-109">Добавление и настройка назначения «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="6b152-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="6b152-110">Перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="6b152-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="6b152-111">В окне **Область элементов SSIS**раскройте элемент **Другие**и перетащите элемент **Назначение «Неструктурированный файл»** в область конструктора потоков данных.</span><span class="sxs-lookup"><span data-stu-id="6b152-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="6b152-112">Поместите **Назначение «Неструктурированный файл»** прямо под преобразованием **Получить описание ошибки** .</span><span class="sxs-lookup"><span data-stu-id="6b152-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="6b152-113">Щелкните преобразование **Получить описание ошибки** и перетащите зеленую стрелку на новый элемент **Назначение "Неструктурированный файл"**.</span><span class="sxs-lookup"><span data-stu-id="6b152-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="6b152-114">В области конструктора **Поток данных** щелкните добавленный элемент **Назначение «Неструктурированный файл»** в только что добавленном преобразовании **Назначение «Неструктурированный файл»** и измените имя на **Строки с ошибками**.</span><span class="sxs-lookup"><span data-stu-id="6b152-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="6b152-115">Щелкните правой кнопкой мыши преобразование **Строки с ошибками** , выберите пункт **Изменить**, а затем в **редакторе назначения "Неструктурированный файл"** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6b152-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="6b152-116">Убедитесь, что в диалоговом окне **Формат неструктурированного файла** выбран параметр **С разделителями** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b152-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="6b152-117">В **Редакторе диспетчера соединений с неструктурированными файлами**в поле **имя диспетчера соединений** введите `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="6b152-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="6b152-118">В диалоговом окне **Редактор диспетчера соединений с неструктурированными файлами** нажмите кнопку **Обзор**и перейдите в папку, в которой будет храниться файл.</span><span class="sxs-lookup"><span data-stu-id="6b152-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="6b152-119">В диалоговом окне **Открыть** в поле **имя файла**введите `ErrorOutput.txt` , а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="6b152-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="6b152-120">В диалоговом окне **Редактор диспетчера соединений с неструктурированными файлами** убедитесь в том, что в поле **Локаль** установлено значение "Английский (США)", а поле **Кодовая страница** содержит значение "1252 (ANSI -Latin I)".</span><span class="sxs-lookup"><span data-stu-id="6b152-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="6b152-121">На панели параметров щелкните **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="6b152-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="6b152-122">Обратите внимание, что, помимо столбцов из исходного файла данных, отображаются три новых столбца: ErrorCode, ErrorColumn и ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="6b152-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="6b152-123">Эти столбцы созданы выходом ошибок преобразования «Уточняющий запрос ключа валют» и скриптом в преобразовании «Получить описание ошибок», они могут использоваться для устранения причин появления ошибочных строк.</span><span class="sxs-lookup"><span data-stu-id="6b152-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="6b152-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b152-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="6b152-125">В диалоговом окне **Редактор назначения «Неструктурированный файл»** снимите флажок **Перезаписать данные в файле** .</span><span class="sxs-lookup"><span data-stu-id="6b152-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="6b152-126">Когда этот флажок снят, сохраняются ошибки выполнения нескольких пакетов.</span><span class="sxs-lookup"><span data-stu-id="6b152-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="6b152-127">В разделе **Редактор назначения «Неструктурированный файл»** щелкните **Сопоставление** , чтобы убедиться, что все столбцы созданы правильно.</span><span class="sxs-lookup"><span data-stu-id="6b152-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="6b152-128">При желании можно переименовать все столбцы назначения.</span><span class="sxs-lookup"><span data-stu-id="6b152-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="6b152-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6b152-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6b152-130">Next Steps</span><span class="sxs-lookup"><span data-stu-id="6b152-130">Next Steps</span></span>  
 [<span data-ttu-id="6b152-131">Шаг 5. Проверка учебного пакета, созданного на занятии 4</span><span class="sxs-lookup"><span data-stu-id="6b152-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  
