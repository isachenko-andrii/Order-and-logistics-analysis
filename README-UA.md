![Project-logo](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/Project-logo.png)
#### [EN](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/README.md) | [UA](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/README-UA.md) Цей матеріал також доступний англійською мовою.
---  
<div align="center">  
    
## Аналіз замовлень та логістики<br>(Power BI Desktop)   
  
</div>  
  
## Опис проекту  

Цей проєкт присвячений створенню інтерактивної та глибокої аналітики для світового рітейлера преміальних делікатесів. На основі реального датасету було розроблено аналітичне рішення в Power BI Desktop, яке дозволяє директору з продажів, логістичним менеджерам та HR-спеціалістам приймати обґрунтовані рішення для підвищення прибутковості та ефективності доставки.  

## Мета та ключові завдання  
  
**Головна мета:** Надати керівництву компанії інструмент для розуміння розподілу замовлень, результатів роботи працівників та ефективності взаємодії з логістичними партнерами.  
  
**Ключові бізнес-запитання:**  
  
 - Які фінансові результати компанії та як вони змінюються з часом?  
 - Які клієнти є найбільш лояльними та прибутковими (ТОП-клієнти)?
 - Наскільки ефективно працюють наші логістичні партнери (Шиппери)? Чи дотримуються вони термінів доставки?  
 - Які результати та рейтинг окремих менеджерів з продажу? Хто надає занадто великі знижки?  

## Методологія та етапи реалізації  
  
Проєкт реалізовано за класичною методологією Business Intelligence (BI):  

**Етап 1. ETL та підготовка даних**  
  
 - **Завантаження та очищення (Power Query):** Дані було завантажено з CSV та TXT файлів, виконано очищення, типізацію та корекцію імен таблиць для бізнес-користувачів.
   
  ![Loading and cleaning](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_1.png)  

  
 - **Календар (DimDate):** Створено окрему таблицю дат (Date table) за допомогою DAX-скрипту, що забезпечує коректну роботу інтелекту часу (time intelligence). Позначено як таблицю дат.

![DimDate_Calendar](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_2.png)  
  
**Етап 2. Моделювання даних (Data Modeling)**  
  
**Архітектура «Зірка»:** Спроектовано оптимальну модель даних, де центральні таблиці фактів (Orders, Order_details) з'єднані з таблицями вимірів (Customers, Employees, Shippers, Products, Categories, Calendar).  
  
![DimDate_Calendar](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_3.png) 
  
**Етап 3. Розрахунки (DAX)**  
  
Розроблено ряд калькульованих полів та складних мір для розрахунку ключових бізнес-метриків, що уміщують логіку:

 - **Фінанси:** Total Sales (з урахуванням кількості, ціни та знижки), Average Discount %.

![Total Sales](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_4.png) 
     
 - **Логістика:** IsLate (обчислюваний стовпець), % On-Time Deliveries, % Late Deliveries.
  
![IsLateDelivery](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_5.png) 
   
  
 - **Обсяги:** Total Orders, Items in Order.

  `Total Orders =   
  DISTINCTCOUNT(fact_orders[orderID])`  
   
**Етап 4. Візуалізація та розробка дашборду (Dashboard Development)**  
 
Створено багатосторінковий інтерактивний звіт із професіональною візуалізацією.  
  
Ключові сторінки звіту:  
  
 - **Фінансовий огляд:** KPI-картки, тренд продажів, географія, ТОП-клієнти.  

![Financial review](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_6.png)  
   
 - **Логістичний аналіз:** Порівняння перевізників за % вчасної доставки та обсягами щороку.  

![Logistics partners](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_7.png)  
  
 - **HR-ефективність:** Результати роботи та рейтинг продажів менеджерів.  

![Employee analysis](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_8.png)  
  
 - **Деталізація (Drill-through):** Прихована сторінка з деталями замовлень для конкретного працівника.  

![Order details](https://github.com/isachenko-andrii/Order-and-logistics-analysis/blob/main/img/ola_9.png)  
  
**Етап 5.** Завантаження та публікація  

 - **Power BI Service:** Звіт опубліковано у хмару в робочу область «global sales workspace».  
  
 - **Інтеграція:** Підготовлено презентацію звітів у PowerPoint та експортовано статичні результати у вигляді слайдів.
 
 - **Ознайомлення** Надано доступ відповідальним особам.  
  
##   
   
## Структура проекту  
  
**Order-and-logistics-analysis**/ — каталог проекту  
├── data/ — дані проєкту  
├── doc/ — технічне завдання  
├── img/ — збережені графіки та дашборди  
├── pbix/ — файли проекту  
├── LICENSE — MIT Ліцензія  
├── project-logo.png — обкладинка проекту  
├── README-UA.md — опис проекту українською мовою   
└── README.md — опис проекту англійською мовою  
  
## Як переглянути проєкт  
  
1. **Попередні вимоги:** Встановіть Power BI Desktop  
2. **Завантаження:** Клонуйте цей репозиторій
3. **Відкриття:** Відкрийте файл `Order and logistics analysis.pbix` у Power BI Desktop
4. **Дані:** За потреби — оновіть джерела даних у Power Query (залежно від того, де ви зберігаєте файли)  
  
## Контакти  
    
**Автор:** [Andrii Isachenko](https://isachenko-andrii.github.io)    
**LinkedIn:** [Andrii Isachenko](https://www.linkedin.com/in/isachenko-andrii/)  
**E-mail:** andrii.isachenko@gmail.com   
  
## Подяки    
  
- Дякую курсу [Аналітик даних/GoIT](https://goit.global/ua/courses/data-analytics/), частиною якого була робота над цим проектом.  
  
---  
  
**Статус проекту:** Виконується.  
    
**Ліцензія:** MIT Ліцензія.  

