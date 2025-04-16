## Студент: Лотфуллин К.Р.

Группа: М05-401

## Дистилляция языковых моделей для анализа кода

### Тема:

По языковым моделям, анализу кода и синтезу комментариев. Большие языковые модели (LLM) показывают неплохие результаты в задачах анализа кода. Однако, возможно ли перенести те же возможности в модель меньшего размера (model distillation)? Нужно разобраться, в каких задачах это получалось сделать и повторить результаты эксперимента.

Ключевые слова: large language models, model distillation, codexglue, CodeBERT, MultiCoder, METASUM, XCode.

### Что мы хотим?

* В каких задачах дистиляция LLM может быть полезна ?  
  ( у меня на работе есть интересная задача что модель учитель учится на офлайн метриках, а ученик учится на онлайн метриках, пытаясь получить знания от учителя)  
* Хотим воспроизвести эксперимент по сжатию моделей, сохрняя качество модели. Например кодогенерация CodeBert to DistilCodeBert.

### Как будем оценивать ?

* Accuracy на задачах классификации кода (CodeXGLUE).  
* BLEU-4 для генерации комментариев (METASUM).  
* CodeBLEU для оценки синтеза кода.  
* Время инференса и размер модели.

### Статейки мои статейки

#### ыNLP задачи

* Суммаризация текста: DistilBART сохраняет 92% качества оригинальной модели при генерации кратких аннотаций. [https://www.restack.io/p/ai-summarization-answer-distilbart-cat-ai](https://www.restack.io/p/ai-summarization-answer-distilbart-cat-ai)  
* Классификация интентов: Дистилляция BERT → TinyBERT для чат-ботов с ускорением инференса в 5x. [https://arxiv.org/abs/1910.01108](https://arxiv.org/abs/1910.01108)  
* Машинный перевод: Сжатие трансформеров (например, mBART-50) для мобильных приложений с потерей BLEU \< 2%. [https://medium.com/@meerakrsna/llm-benchmarks-for-coding-dc2b4f2a1879](https://medium.com/@meerakrsna/llm-benchmarks-for-coding-dc2b4f2a1879)

#### дистиляция

* Обзор методов дистилляции для NLP: [Hinton et al., 2015](https://arxiv.org/abs/1503.02531).  
* Применение Shuffled Parameter Sharing (SPS) для повышения эффективности студенческих моделей: [Pea-KD](https://www.arxiv-vanity.com/papers/2009.14822/).  
* Дистилляция BERT в DistilBERT с сохранением 97% точности: [Sanh et al., 2019](https://arxiv.org/abs/1910.01108).

#### 	Анализ кода

* CodeBERT: бимодальная модель для кода и естественного языка: [Feng et al., 2020](https://arxiv.org/abs/2002.08155).  
* Многоязычный анализ кода с помощью MultiCoder: [Chakraborty et al., 2022](https://arxiv.org/abs/2206.08417).  
* METASUM: мета-обучение для генерации комментариев: [Liu et al., 2021](https://arxiv.org/abs/2103.07115).

### Бенчмарки

* CodeXGLUE: набор задач для оценки моделей анализа кода: [Lu et al., 2021](https://arxiv.org/abs/2102.04664).  
* HumanEval: тестирование функциональной корректности кода: [Chen et al., 2021](https://arxiv.org/abs/2107.03374).

### Что мы знаем (ну конкретно я)

* Деградация качества.  
* Переобучение на синтетике  
* Недостаток контекста (типа не знает все фичи)

### Чисто Теория

* «MiniLLM: Knowledge Distillation of Large Language Models» (2023)  
  Дистилляция GPT-3.5 в модели размером 1.3B параметров. Решение проблемы «глубины знаний» через RLHF.  
  [\[2306.08843\] Real-Time Network-Level Traffic Signal Control: An Explicit Multiagent Coordination Method](https://arxiv.org/abs/2306.08843)  
* «Distilling Step-by-Step\!» (Hsieh et al., 2023\)  
  Поэтапная дистилляция с объяснениями (Chain-of-Thought). Улучшение на 15% для задач генерации кода.  
  [\[2305.02301\] Distilling Step-by-Step\! Outperforming Larger Language Models with Less Training Data and Smaller Model Sizes](https://arxiv.org/abs/2305.02301)  
* «The Efficiency Paradox in Model Distillation» (Wang et al., 2024\)  
  Анализ компромисса между размером модели и качеством. Доказательство предела дистилляции для LLM (минимальный размер \= 12% от учителя).  
  [\[2403.01788\] K-stars LDP: A Novel Framework for (p, q)-clique Enumeration under Local Differential Privacy](https://arxiv.org/abs/2403.01788)  
* «Knowledge Distillation from Foundation Models» (Snorkel AI, 2023\)  
  Практическое руководство по дистилляции GPT-4 для enterprise-задач. Снижение стоимости инференса на 90%.  
  [LLM distillation techniques to explode in importance in 2024](https://snorkel.ai/blog/llm-distillation-techniques-to-explode-in-importance-in-2024/)

### Примеры

* CodeBERT to DistilCodeBERT: [arXiv:1910.10683v4 \[cs.LG\] 19 Sep 2023](https://arxiv.org/pdf/1910.10683)  
* METASUM: дистиляция моделей [AI Summarization Distilbart | Restackio](https://www.restack.io/p/ai-summarization-answer-distilbart-cat-ai).  
* На маленьких устройствах :[LLM Distillation: Optimizing Large Language Models for Efficiency \- DEV Community](https://dev.to/es404020/llm-distillation-optimizing-large-language-models-for-efficiency-2141).


