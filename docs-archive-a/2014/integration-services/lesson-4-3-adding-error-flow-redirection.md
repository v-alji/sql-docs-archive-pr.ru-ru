---
title: Шаг 3. Добавление перенаправления потока ошибок | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658890"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="65f2a-102">Шаг 3. Добавление перенаправления потока ошибок</span><span class="sxs-lookup"><span data-stu-id="65f2a-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="65f2a-103">Как было рассмотрено в предыдущей задаче, преобразование «Поиск ключа валюты» при попытке обработать поврежденный образец неструктурированного файла не может сформировать соответствие. Вместо этого формируется ошибка.</span><span class="sxs-lookup"><span data-stu-id="65f2a-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="65f2a-104">Поскольку преобразование использует установки по умолчанию для вывода ошибки, любая возникшая ошибка приводит к неудачному завершению преобразования.</span><span class="sxs-lookup"><span data-stu-id="65f2a-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="65f2a-105">При неудачном завершении преобразования выполнение пакета также завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="65f2a-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="65f2a-106">Чтобы предотвратить завершение преобразования с ошибкой, можно настроить вывод ошибок в этом компоненте таким образом, чтобы строка с ошибкой перенаправлялась на другой путь обработки.</span><span class="sxs-lookup"><span data-stu-id="65f2a-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="65f2a-107">Использование отдельного пути обработки ошибок позволяет решить сразу несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="65f2a-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="65f2a-108">Например, можно попытаться очистить данные, а затем заново обработать строку с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="65f2a-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="65f2a-109">Можно также сохранить строку с ошибкой вместе с дополнительными сведениями об ошибке для последующей проверки и повторной обработки.</span><span class="sxs-lookup"><span data-stu-id="65f2a-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="65f2a-110">В этой задаче будет настроено преобразование «Поиск ключа валюты» так, чтобы все строки с ошибками перенаправлялись на вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="65f2a-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="65f2a-111">Согласно ветке ошибок потока данных, эти строки будут записаны в файл.</span><span class="sxs-lookup"><span data-stu-id="65f2a-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="65f2a-112">По умолчанию два дополнительных столбца в выводе ошибок служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , **ErrorCode** и **ErrorColumn**, содержат только числовые коды, представляющие номер ошибки и идентификатор столбца, в котором произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="65f2a-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="65f2a-113">Эти числовые значения могут быть малополезны без соответствующего описания ошибки.</span><span class="sxs-lookup"><span data-stu-id="65f2a-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="65f2a-114">Чтобы повысить информативность вывода ошибок, перед тем как пакет запишет строки с ошибками в файл, следует с помощью компонента скрипта получить доступ к API-интерфейсу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и извлечь описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="65f2a-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="65f2a-115">Настройка выхода ошибок</span><span class="sxs-lookup"><span data-stu-id="65f2a-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="65f2a-116">В **области элементов служб SSIS**разверните **узел Общие**и перетащите **компонент Скрипт** в область конструктора на вкладке **поток данных** . Поместите **Скрипт** справа от преобразования **Поиск ключа валюты** .</span><span class="sxs-lookup"><span data-stu-id="65f2a-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="65f2a-117">В диалоговом окне **Выбор типа компонента скрипта** выберите **Преобразование**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65f2a-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="65f2a-118">Щелкните преобразование **Поиск ключа валюты** и перетащите красную стрелку на вновь созданное преобразование **Скрипт** , соединив эти два компонента.</span><span class="sxs-lookup"><span data-stu-id="65f2a-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="65f2a-119">Красная стрелка отображает вывод ошибок преобразования **Поиск ключа валюты** .</span><span class="sxs-lookup"><span data-stu-id="65f2a-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="65f2a-120">Используя красную стрелку для подключения преобразования к компоненту скрипта, можно перенаправить любые ошибки обработки компоненту скрипта, который обрабатывает их и отправляет по назначению.</span><span class="sxs-lookup"><span data-stu-id="65f2a-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="65f2a-121">В диалоговом окне **Настройка вывода ошибок** в столбце **Ошибка** выберите **Перенаправить строку**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65f2a-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="65f2a-122">В области конструктора **Поток данных** щелкните элемент **Компонент скрипта** в только что добавленном преобразовании **ScriptComponent**и измените имя на **Получение описания ошибки**.</span><span class="sxs-lookup"><span data-stu-id="65f2a-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="65f2a-123">Дважды щелкните преобразование **Получение описания ошибки** .</span><span class="sxs-lookup"><span data-stu-id="65f2a-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="65f2a-124">В диалоговом окне **Редактор преобразования «Скрипт»** на странице **Входные столбцы** выберите столбец **ErrorCode** .</span><span class="sxs-lookup"><span data-stu-id="65f2a-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="65f2a-125">На странице **Входы и выходы** раскройте **Выход 0**, выберите **Выходные столбцы**и нажмите кнопку **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="65f2a-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="65f2a-126">В `Name` свойстве введите **ErrorDescription** и задайте `DataType` для свойства значение **строка Юникода [DT_WSTR]**.</span><span class="sxs-lookup"><span data-stu-id="65f2a-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="65f2a-127">На странице **Скрипт** убедитесь, что `LocaleID` свойство имеет значение **Английский (США.**</span><span class="sxs-lookup"><span data-stu-id="65f2a-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="65f2a-128">Нажмите кнопку **Изменить скрипт**, чтобы открыть среду [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="65f2a-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="65f2a-129">В методе `Input0_ProcessInputRow` введите или вставьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="65f2a-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="65f2a-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="65f2a-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="65f2a-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="65f2a-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="65f2a-132">Готовая подпрограмма должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="65f2a-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="65f2a-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="65f2a-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="65f2a-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="65f2a-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="65f2a-135">В меню **Построение** выберите команду **Построить решение** , чтобы создать скрипт и сохранить изменения, а затем закройте средства VSTA.</span><span class="sxs-lookup"><span data-stu-id="65f2a-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="65f2a-136">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Редактор преобразования «Скрипт»** .</span><span class="sxs-lookup"><span data-stu-id="65f2a-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="65f2a-137">Next Steps</span><span class="sxs-lookup"><span data-stu-id="65f2a-137">Next Steps</span></span>  
 <span data-ttu-id="65f2a-138">[Шаг 4. Добавление назначения «Неструктурированный файл»] (lesson-4-4-adding-a-flat-file-destination.md</span><span class="sxs-lookup"><span data-stu-id="65f2a-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
