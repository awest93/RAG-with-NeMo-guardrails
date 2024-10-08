# RAG-with-NeMo-guardrails

Выполняется задача по созданию нейро-ассистента для аптеки. Ассистент выполняет функции по поиску лекарств на основе описания симптомов и отвечает сколько на складе ещё осталось единиц лекарства. В качестве документа для формирования векторной БД и поиска информации, используется небольшой структурированный список лекрств с их описанием и указанием оставшегося на складе количества.

БД системы основана на списке лекарств размещённом по адресу: https://docs.google.com/document/d/1TLpon7m5oR2VvjbsDmoQyTsoFsLtojr2v5xh8qvg0kY/edit?usp=sharing

В качестве модели эмбеддингов используется модель с huggingface - "sentence-transformers/all-MiniLM-L12-v2".

В качестве основной LLM для RAG используется русскоязычная модель с huggingface - "IlyaGusev/saiga_mistral_7b".

В качестве постобработки используется преобразование предложений (Sentence Transformer).

В качестве модератора используется NeMo Guardrails.

Для работы модератора используется API модели с huggingface - "mistralai/Mistral-7B-Instruct-v0.3". Работа с API требуется для возможности работать с моделью без её загрузки в память видеоадаптера, а также потому что эта модель в отличии от основной корректно отвечает на запросы в роли модератора.
