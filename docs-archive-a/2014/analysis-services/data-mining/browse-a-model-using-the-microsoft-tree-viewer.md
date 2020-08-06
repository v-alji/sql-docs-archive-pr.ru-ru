---
title: Просмотр модели с помощью средства просмотра деревьев (Майкрософт) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Tree Viewer [Analysis Services]
- predictions [Analysis Services], discrete attributes
- mining model content, viewing
- predictions [Analysis Services], continuous attributes
- mining legend [Analysis Services]
- discrete attributes [Analysis Services]
- Microsoft Decision Trees algorithm [Analysis Services]
- decision tree algorithms [Analysis Services]
- Microsoft Tree Viewer
- decision trees [Analysis Services]
- dependencies [Analysis Services]
- continuous attributes
ms.assetid: 0c96d518-ed20-40b7-8d62-b26ad6244287
author: minewiskan
ms.author: owend
ms.openlocfilehash: cebe1e05435fad453757b4f747ae809f379c410f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669198"
---
# <a name="browse-a-model-using-the-microsoft-tree-viewer"></a>Просмотр модели с помощью средства просмотра деревьев (Майкрософт)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]Средство просмотра деревьев в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] отображает деревья решений, построенные с помощью [!INCLUDE[msCoName](../../includes/msconame-md.md)] алгоритма дерева принятия решений. Алгоритм дерева принятия решений [!INCLUDE[msCoName](../../includes/msconame-md.md)] — это гибридный алгоритм дерева принятия решений, который поддерживает и классификацию, и регрессию. Поэтому это средство просмотра можно использовать для просмотра моделей, основанных на алгоритме линейной регрессии [!INCLUDE[msCoName](../../includes/msconame-md.md)] . Алгоритм дерева принятия решений [!INCLUDE[msCoName](../../includes/msconame-md.md)] используется для прогнозирующего моделирования дискретных и непрерывных атрибутов. Дополнительные сведения об этом алгоритме см. в разделе [Microsoft Decision Trees Algorithm](microsoft-decision-trees-algorithm.md).  
  
> [!NOTE]  
>  Чтобы просмотреть подробные сведения об использованных в модели уравнениях и обнаруженных закономерностях, используйте средство просмотра деревьев содержимого общего вида [!INCLUDE[msCoName](../../includes/msconame-md.md)] . Дополнительные сведения см. в разделах [Просмотр модели в средстве просмотра деревьев содержимого общего вида (Майкрософт)](browse-a-model-using-the-microsoft-generic-content-tree-viewer.md) и [Средство просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных)](../microsoft-generic-content-tree-viewer-data-mining.md).  
  
##  <a name="viewer-tabs"></a><a name="BKMK_TabsPanes"></a>Вкладки средства просмотра  
 При просмотре модели интеллектуального анализа данных в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]модель отображается на вкладке **Средство просмотра моделей интеллектуального анализа данных** конструктора интеллектуального анализа данных с использованием соответствующего средства просмотра для данной модели. Средство просмотра деревьев [!INCLUDE[msCoName](../../includes/msconame-md.md)] содержит следующие вкладки и панели:  
  
-   [Дерево принятия решений](#BKMK_DecisionTree)  
  
-   [Сеть зависимостей](#BKMK_DependencyNetwork)  
  
-   [Условные обозначения интеллектуального анализа данных](#BKMK_MiningLegend)  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a>Дерево принятия решений  
 Во время построения модели дерева решений службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] строят отдельное дерево для каждого прогнозируемого атрибута. Отдельное дерево можно просмотреть, выбрав его из списка **Дерево** на вкладке **Дерево решений** средства просмотра.  
  
 Дерево решений состоит из серии разбиений, где наиболее важное разбиение, определенное алгоритмом, находится в левой части средства просмотра в узле **Все** . Дополнительные разбиения расположены справа. Разбиение в узле **Все** является наиболее важным, так как оно содержит самое строгое условие создания разбиений в наборе данных и поэтому приводит к созданию первого разбиения.  
  
 Индивидуальные узлы в дереве можно развернуть или свернуть, чтобы отобразить или скрыть разбиения, происходящие после каждого узла. Кроме этого, можно воспользоваться параметром на вкладке **Дерево решений** для изменения способа отображения дерева. Используйте ползунок **Показать уровень** для установки количества уровней, отображаемых в дереве. Используйте ползунок **Расширение по умолчанию** для установки количества уровней по умолчанию, которые отображаются для всех деревьев в модели.  
  
#### <a name="predicting-discrete-attributes"></a>Прогнозирование дискретных атрибутов  
 Когда дерево строится с дискретным прогнозируемым атрибутом, средства просмотра отображают для каждого узла дерева следующие данные.  
  
-   Условие, вызвавшее разбиение.  
  
-   Гистограмма, которая представляет распределение состояний прогнозируемого атрибута, в порядке распространенности.  
  
 Можно использовать параметр **Гистограмма** , чтобы изменить число состояний, которые показываются в гистограммах дерева. Это полезно, когда у прогнозируемого атрибута много состояний. Состояния появляются на гистограмме упорядоченными по степени распространенности, слева направо. Если число состояний, указанных для отображения, меньше, чем полное число состояний атрибута, наименее часто встречающиеся состояния будут отображены вместе серым цветом. Чтобы увидеть точное число для каждого состояния узла, остановите указатель над узлом, чтобы увидеть подсказку, или выберите узел, подробности по которому необходимо получить, в области **Обозначения интеллектуального анализа данных**.  
  
 Цвет фона каждого узла представляет концентрацию случаев наличия конкретного состояния атрибута, который выбирается в параметре **Фон** . Можно использовать этот параметр для выделения узлов, содержащих представляющие интерес цели.  
  
#### <a name="predicting-continuous-attributes"></a>Прогнозирование непрерывных атрибутов  
 При построении дерева с непрерывным прогнозируемым атрибутом средство просмотра отображает для каждого узла дерева ромбовидную диаграмму вместо гистограммы. Ромбовидная диаграмма содержит строку, представляющую диапазон атрибута. Ромб расположен в среднем значении для узла, а ширина ромба представляет дисперсию атрибута в этом узле. Более узкий ромб указывает, что узел способен создавать более точный прогноз. Средство просмотра также отображает формулу регрессии, которая используется для определения разбиения в узле.  
  
#### <a name="additional-decision-tree-display-options"></a>Дополнительные параметры отображения дерева решений  
 Когда для модели дерева решений включена детализация, можно обращаться к обучающим вариантам, которые поддерживают узел, щелкнув его правой кнопкой мыши и выбрав пункт **Детализация**. Можно включить детализацию в мастере интеллектуального анализа данных или путем настройки параметра детализации для модели интеллектуального анализа данных на вкладке **Модели интеллектуального анализа данных** .  
  
 Можно использовать параметры масштабирования на вкладке **Дерево решений** , чтобы увеличить или уменьшить дерево, или же использовать функцию **Подогнать размер** , чтобы на экране обозревателя помещалась модель целиком. Если дерево слишком велико, чтобы уместиться на экране, можно воспользоваться параметром **Навигация**для перемещения по дереву. При выборе пункта **Навигация** открывается отдельное окно обзора, в котором можно выбирать разделы модели, которые будут отображаться.  
  
 Также можно скопировать изображение представления дерева в буфер обмена, а затем вставить его в документах или программе для работы с изображениями. Используйте функцию **Копировать представление диаграммы** , чтобы скопировать только тот раздел дерева, который виден пользователю, а функцию **Копировать всю диаграмму** — для копирования всех раскрытых узлов дерева.  
  
 [К началу](#BKMK_TabsPanes)  
  
###  <a name="dependency-network"></a><a name="BKMK_DependencyNetwork"></a>Сеть зависимостей  
 Окно **Сеть зависимостей** отображает зависимости между входными атрибутами и прогнозируемыми атрибутами модели. Ползунок слева от средства просмотра выступает в качестве фильтра, привязанного к прочности зависимостей. Если перемещать ползунок ниже, будут видны только наиболее прочные из них.  
  
 После выбора узла в средстве просмотра выделяются зависимости, относящиеся к узлу. Например, при выборе прогнозируемого узла в средстве просмотра также выделяется каждый узел, оказывающий содействие в прогнозировании этого узла.  
  
 Если в средстве просмотра содержится много узлов, можно найти нужные с помощью кнопки **Найти узел** . После нажатия кнопки **Найти узел** откроется диалоговое окно **Поиск узла** , где можно использовать фильтр для поиска и выбора нужных узлов.  
  
 Условные обозначения в нижней части средства просмотра связывают цветовые коды с типом зависимости на графе. Например, при выборе прогнозируемого узла он выделяется бирюзовым цветом, а узлы, которые прогнозируют выбранный узел, — оранжевым цветом.  
  
 [К началу](#BKMK_TabsPanes)  
  
###  <a name="mining-legend"></a><a name="BKMK_MiningLegend"></a>Условные обозначения интеллектуального анализа данных  
 **Обозначения интеллектуального анализа данных** отображают следующие сведения, если выбран узел в модели дерева принятия решений.  
  
-   Количество вариантов в узле, упорядоченные по состояниям прогнозируемого атрибута.  
  
-   Вероятность каждого варианта прогнозируемого атрибута для узла.  
  
-   Гистограмма, которая содержит счетчик для каждого состояния прогнозируемого атрибута.  
  
-   Условия, необходимые, чтобы достичь определенного узла, также известные как *путь узла*.  
  
-   Для моделей линейной регрессии — формула регрессии.  
  
 Можно прикреплять окно **Обозначения интеллектуального анализа данных** и работать с ним так же, как с обозревателем решений.  
  
 [К началу](#BKMK_TabsPanes)  
  
## <a name="see-also"></a>См. также:  
 [Алгоритм дерева принятия решений (Майкрософт)](microsoft-decision-trees-algorithm.md)   
 [Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](../mining-model-viewers-data-mining-model-designer.md)   
 [Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](mining-model-viewer-tasks-and-how-tos.md)   
 [Средства интеллектуального анализа данных](data-mining-tools.md)   
 [Средства просмотра моделей интеллектуального анализа данных](data-mining-model-viewers.md)  
  
  