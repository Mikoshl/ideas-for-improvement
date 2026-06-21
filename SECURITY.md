const solutions = [
  {
    id: 1, category: "intelligence", categoryName: "Данные и аналитика", icon: "100%", color: "#00a6ff", featured: true,
    title: "Автоматический разбор звонков", short: "Предлагаю анализировать не небольшую выборку прослушек, а весь доступный поток звонков из Smart Logger.",
    lead: "Система внутри корпоративной среды расшифровывает звонки, скрывает персональные данные, находит тему обращения и отмечает признаки возможного повторного звонка.",
    problems: ["Ручные прослушки охватывают малую выборку", "Причины повторки выявляются слишком поздно", "Нет единой аналитики по всему потоку"],
    how: ["Расшифровывает звонок и маскирует ПДн", "Определяет тему и признаки повторного обращения", "Сверяет действия оператора с инструкцией КМ", "Формирует понятную карточку для супервайзера"],
    effect: "Полный охват звонков, меньше ручной нагрузки и быстрый поиск реальных причин повторной обращаемости."
  },
  {
    id: 2, category: "service", categoryName: "Работа с клиентом", icon: "СРОК", color: "#e72487", featured: true,
    title: "Контроль обещаний клиенту", short: "Если известен статус заявки, массовая проблема или риск просрочки, клиент получает информацию до повторного звонка.",
    lead: "Если компания уже знает статус, проблему или риск просрочки, клиент не должен звонить в контакт-центр, чтобы узнать это самостоятельно.",
    problems: ["Звонки по статусу заявки", "Массовые звонки во время инцидента", "Недоверие при нарушении обещанного срока"],
    how: ["Отслеживает SLA и статус заявки", "Определяет реально затронутых клиентов", "Отправляет Push до звонка в 611", "Запускает извинение или бонус по правилу"],
    effect: "Меньше звонков по статусам и массовым сбоям, меньше дублей, выше доверие клиента."
  },
  {
    id: 3, category: "people", categoryName: "Операторы и процессы", icon: "✓", color: "#43d59e",
    title: "Умная диагностика", short: "Диагностика интернета с первого обращения и чек-лист правильного закрытия звонка.",
    lead: "Процесс перестаёт генерировать повторные обращения: настройки отправляются только тогда, когда проблема действительно в них.",
    problems: ["Настройки отправляются по умолчанию", "Заявка создаётся только после нескольких звонков", "Клиент не понимает срок и следующий шаг"],
    how: ["Проверяет настройки устройства в CRM", "Показывает ошибки БС через Solution Checker", "Даёт оператору точную причину и срок", "Закрывает разговор тремя контрольными вопросами"],
    effect: "Меньше повторных звонков по интернету и выше доля полноценного решения с первого обращения."
  },
  {
    id: 4, category: "service", categoryName: "Работа с клиентом", icon: "↻", color: "#e72487", featured: true,
    title: "Работа с повторным клиентом", short: "При повторном звонке оператор сразу видит историю, обещания, номер заявки, SLA и правильный следующий шаг.",
    lead: "Клиент не объясняет проблему заново, а оператор сразу видит обещания, заявку, SLA, ответственный отдел и допустимое следующее действие.",
    problems: ["Повторный клиент попадает в обычную очередь", "Каждый оператор начинает разбор заново", "Создаются дубли заявок"],
    how: ["Распознаёт повтор по теме и клиенту", "Показывает историю и блокирует дубль", "Повышает приоритет на втором повторе", "Передаёт кейс специальной команде на третьем"],
    effect: "Быстрее решаются сложные кейсы, снижаются дубли и повторные обращения по одной теме."
  },
  {
    id: 5, category: "people", categoryName: "Операторы и процессы", icon: "ТР", color: "#ffb64b",
    title: "Тренажёр сложных звонков", short: "Оператор отрабатывает сценарии повторных обращений, проблем с интернетом, просроченных заявок и компенсаций.",
    lead: "Обучение заканчивается не отметкой об участии, а подтверждённым навыком на реальном звонке.",
    problems: ["Теория не меняет поведение", "Ошибки повторяются после обратной связи", "Нет подтверждения полученного навыка"],
    how: ["Система разыгрывает диалог со сложным клиентом", "Оценивает диагностику, эмпатию и закрытие", "Назначает короткое обучение после ошибки", "Проверяет навык контрольной прослушкой"],
    effect: "Быстрее адаптация, меньше повторных ошибок и измеримый coaching loop."
  },
  {
    id: 6, category: "intelligence", categoryName: "Данные и аналитика", icon: "KZ", color: "#e72487",
    title: "Карта жалоб по Казахстану", short: "На карте видно, из каких регионов растут обращения, где повторяются жалобы и какие инциденты на БС могут быть причиной.",
    lead: "Единая география клиентской боли показывает не только где много звонков, но и какой технический фактор их создаёт.",
    problems: ["Региональные проблемы скрыты в агрегатах", "КЦ и техблок смотрят разные отчёты", "Эффект работ не связан с жалобами"],
    how: ["Объединяет звонки, заявки, БС и CSI", "Показывает кластеры и динамику", "Фильтрует по теме, периоду и региону", "Сравнивает показатели до и после работ"],
    effect: "Точечные модернизации на основе данных по жалобам и прозрачный контроль результата."
  },
  {
    id: 7, category: "intelligence", categoryName: "Данные и аналитика", icon: "!", color: "#e72487",
    title: "Раннее предупреждение", short: "Резкий рост звонков по одной теме или региону фиксируется до того, как очередь на линии заметно увеличится.",
    lead: "Рост фраз «не работает», обращений по одной БС или повторки становится автоматическим триггером реакции.",
    problems: ["Инцидент виден только после всплеска звонков", "Клиенты узнают о проблеме раньше оператора", "Реакция отделов запускается вручную"],
    how: ["Отслеживает всплески за 30–60 минут", "Сверяет звонки с техническими событиями", "Создаёт инцидент и уведомляет команды", "Запускает Promise Keeper"],
    effect: "Быстрее реакция, меньше пиковая нагрузка на 611 и больше клиентов, уведомлённых заранее."
  },
  {
    id: 8, category: "service", categoryName: "Работа с клиентом", icon: "→", color: "#00a6ff",
    title: "Подсказка следующего действия", short: "Во время разговора оператор получает конкретную подсказку: не создавать дубль, назвать срок, открыть нужную инструкцию или передать случай в специальную команду.",
    lead: "Система предупреждает об активной заявке, проблеме БС, сроке, инструкции КМ и необходимости передачи в специальную команду.",
    problems: ["Оператор ищет данные в нескольких системах", "Решение зависит от опыта сотрудника", "Создаются ошибки и дубли"],
    how: ["Собирает контекст клиента в реальном времени", "Сопоставляет его с КМ и инцидентами", "Предлагает одно следующее действие", "Контролирует финальное закрытие"],
    effect: "Быстрее консультация, меньше ошибок и проще адаптация новых сотрудников."
  },
  {
    id: 9, category: "intelligence", categoryName: "Данные и аналитика", icon: "ОБЗ", color: "#00a6ff",
    title: "Единый обзор обращений", short: "Звонки, жалобы, заявки, CSI/NPS, технические сбои и компенсации собираются в одном отчёте вместо нескольких несвязанных файлов.",
    lead: "Звонки, жалобы, заявки, CSI/NPS, технические сбои и компенсации складываются в одну причинно-следственную картину.",
    problems: ["Отчёты не связаны между собой", "Не видны корневые процессные причины", "Решения принимаются на частичных данных"],
    how: ["Объединяет источники в общей модели", "Строит топ причин и проблемных процессов", "Связывает КМ, БС, CSI и повторку", "Показывает эффект действий"],
    effect: "Быстрее управленческие решения и единая версия правды о клиентской боли."
  },
  {
    id: 10, category: "people", categoryName: "Операторы и процессы", icon: "ДО/ПОСЛЕ", color: "#43d59e",
    title: "Проверка эффекта модернизаций", short: "После работ проверяется не только техническое закрытие, но и снижение жалоб, повторных звонков и компенсаций.",
    lead: "Техническое закрытие работ дополняется измерением клиентского эффекта: жалобы, повторка, CSI и компенсации.",
    problems: ["Работы закрыты, а жалобы продолжаются", "Нет клиентского критерия успеха", "Эффект модернизации не доказан"],
    how: ["Фиксирует baseline до работ", "Сравнивает жалобы и повторку после", "Отслеживает CSI и компенсации", "Возвращает проблему в работу при отсутствии эффекта"],
    effect: "Инвестиции в сеть связываются с измеримым улучшением клиентского опыта."
  }
];

const solutionEstimates = {
  1: {
    duration: "16–24 недели", teamSize: "6–8 специалистов", budget: "40–80 млн ₸",
    tech: ["Доступ к записям Smart Logger и метаданным звонка", "Внутренняя транскрибация и модуль маскирования ПДн", "Классификатор тем, повторки и соблюдения КМ", "Витрина данных, карточка супервайзера и аудит решений"],
    team: "Владелец продукта, бизнес-аналитик КЦ, data engineer, ML/NLP-инженер, backend-разработчик, BI/frontend, QA, DevOps и ИБ.",
    metrics: [{ value: "100%", label: "доступных звонков в анализе" }, { value: "−50–70%", label: "ручного времени на поиск кейсов" }, { value: "−1–3 п.п.", label: "цель снижения повторки в пилоте" }]
  },
  2: {
    duration: "10–16 недель", teamSize: "4–6 специалистов", budget: "18–40 млн ₸",
    tech: ["События по заявкам, SLA и массовым инцидентам", "Правила определения затронутых клиентов", "Шаблоны Push/SMS и согласование юридических текстов", "Механизм компенсации и контроль факта доставки"],
    team: "Владелец процесса, бизнес-аналитик, backend-интегратор, CRM-разработчик, специалист Push/SMS, QA и ИБ.",
    metrics: [{ value: "−15–30%", label: "звонков по статусу заявки" }, { value: "−10–25%", label: "пиковых звонков при инциденте" }, { value: "+5–10", label: "потенциал роста CSI по кейсам" }]
  },
  3: {
    duration: "12–20 недель", teamSize: "5–7 специалистов", budget: "22–48 млн ₸",
    tech: ["Разметка 1 000 обращений по отсутствию интернета", "Интеграция CRM с диагностикой устройства и данными БС", "Правила, когда настройки действительно нужны", "Чек-лист закрытия и контроль повторного звонка"],
    team: "Эксперт по интернету/БС, бизнес-аналитик, CRM-разработчик, backend, инженер интеграций, QA и тренер КЦ.",
    metrics: [{ value: "−10–20%", label: "повторки по интернету" }, { value: "−20–40%", label: "лишних отправок настроек" }, { value: "+5–12 п.п.", label: "FCR по выбранным сценариям" }]
  },
  4: {
    duration: "12–20 недель", teamSize: "5–7 специалистов", budget: "28–58 млн ₸",
    tech: ["Алгоритм определения повтора по клиенту, теме и периоду", "Единая карточка истории, SLA и обещаний", "Блокировка дубля и правила приоритета", "Очередь Repeat Rescue и назначение владельца"],
    team: "Владелец сервиса, аналитик, CRM-разработчик, backend, интегратор заявок, frontend, QA и руководитель специальной команды.",
    metrics: [{ value: "−20–35%", label: "дублирующих заявок" }, { value: "−10–20%", label: "третьих и последующих звонков" }, { value: "−15–25%", label: "времени решения сложного кейса" }]
  },
  5: {
    duration: "8–14 недель", teamSize: "4–6 специалистов", budget: "14–32 млн ₸",
    tech: ["Библиотека сценариев на основе причин повторки", "Тренировочный диалог и критерии оценки", "Связь ошибки с коротким обучающим модулем", "Контрольная прослушка через 3–7 дней"],
    team: "Методолог, тренер КЦ, бизнес-аналитик, frontend/backend-разработчик, специалист по диалоговым моделям и QA.",
    metrics: [{ value: "−10–20%", label: "повторных ошибок после обучения" }, { value: "−15–25%", label: "срока адаптации новичка" }, { value: "+15–30%", label: "закрытых циклов обратной связи" }]
  },
  6: {
    duration: "10–16 недель", teamSize: "5–7 специалистов", budget: "20–45 млн ₸",
    tech: ["Геопривязка звонков, заявок и инцидентов без публикации ПДн", "Витрина по области, городу, селу и кластеру БС", "Пороговые правила красных зон", "Сравнение до/после модернизации"],
    team: "Data engineer, GIS/BI-разработчик, backend, frontend, аналитик КЦ, эксперт техблока и QA.",
    metrics: [{ value: "−30–50%", label: "времени поиска проблемной территории" }, { value: "−10–20%", label: "повторки в пилотных зонах" }, { value: "100%", label: "модернизаций с клиентским замером" }]
  },
  7: {
    duration: "12–20 недель", teamSize: "5–7 специалистов", budget: "24–50 млн ₸",
    tech: ["Поток событий по звонкам каждые 5–15 минут", "Пороговые и статистические правила аномалий", "Сверка с инцидентами БС", "Алерт КЦ/техблоку и запуск уведомлений"],
    team: "Data engineer, backend, аналитик аномалий, инженер мониторинга, DevOps, QA и представители КЦ/техблока.",
    metrics: [{ value: "−30–60%", label: "времени обнаружения проблемы" }, { value: "−10–25%", label: "пиковых звонков" }, { value: "+20–40%", label: "клиентов, предупреждённых заранее" }]
  },
  8: {
    duration: "16–24 недели", teamSize: "6–9 специалистов", budget: "35–75 млн ₸",
    tech: ["Сбор контекста клиента из CRM, КМ и заявок", "Набор правил следующего действия", "Встраивание подсказки в рабочее окно оператора", "A/B-пилот и контроль неверных рекомендаций"],
    team: "Product owner, аналитик КЦ, CRM/frontend-разработчик, backend, интегратор КМ, QA, UX и ИБ.",
    metrics: [{ value: "−10–20%", label: "процессных ошибок" }, { value: "−3–8%", label: "AHT на пилотных темах" }, { value: "+5–10 п.п.", label: "FCR новых операторов" }]
  },
  9: {
    duration: "12–20 недель", teamSize: "5–7 специалистов", budget: "28–55 млн ₸",
    tech: ["Единая модель звонка, жалобы, заявки и CSI/NPS", "Витрина причин обращений и повторки", "Ролевые отчёты для КЦ, качества и техблока", "Регламент владельцев показателей"],
    team: "Владелец данных, бизнес-аналитик, data engineer, BI-разработчик, backend, QA и представители подразделений.",
    metrics: [{ value: "−50–70%", label: "времени на сбор отчётности" }, { value: "1", label: "согласованная версия показателей" }, { value: "еженедельно", label: "контроль корневых причин" }]
  },
  10: {
    duration: "8–14 недель", teamSize: "4–6 специалистов", budget: "14–30 млн ₸",
    tech: ["Фиксация baseline до модернизации", "Привязка работ к БС, территории и теме жалобы", "Автоматический замер через 7/30/60 дней", "Возврат задачи в работу при отсутствии эффекта"],
    team: "Аналитик, data engineer, BI-разработчик, backend, QA и владелец процесса модернизации.",
    metrics: [{ value: "100%", label: "работ с замером клиентского эффекта" }, { value: "−10–20%", label: "жалоб в успешных зонах" }, { value: "7/30/60", label: "дней контрольного замера" }]
  }
};

const solutionsGrid = document.querySelector("#solutionsGrid");
const categoryLabels = { intelligence: "Данные", service: "Клиент", people: "Процесс" };

function renderSolutions(filter = "all") {
  solutionsGrid.innerHTML = solutions
    .filter(item => filter === "all" || item.category === filter)
    .map(item => `
      <article class="solution-card${item.featured && filter === "all" ? " featured" : ""}" style="--card-accent:${item.color}" tabindex="0" data-id="${item.id}" aria-label="Подробнее: ${item.title}">
        <div class="card-top"><span class="card-index">${String(item.id).padStart(2, "0")}</span><span class="card-category">${categoryLabels[item.category]}</span></div>
        <span class="card-icon">${item.icon}</span>
        <h3>${item.title}</h3>
        <p>${item.short}</p>
        <div class="card-details"><span>Как это может работать</span><ul>${item.how.slice(0, 3).map(text => `<li>${text}</li>`).join("")}</ul></div>
        <div class="card-effect"><strong>Ожидаемый результат</strong><span>${item.effect}</span></div>
        <div class="card-invest"><span><small>Пилот</small>${solutionEstimates[item.id].duration}</span><span><small>Бюджет</small>${solutionEstimates[item.id].budget}</span><span><small>Главный KPI</small>${solutionEstimates[item.id].metrics[0].value}</span></div>
        <span class="card-link">Подробное описание →</span>
      </article>`).join("");
}

renderSolutions();

document.querySelectorAll(".filter-button").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".filter-button").forEach(item => item.classList.remove("active"));
    button.classList.add("active");
    renderSolutions(button.dataset.filter);
  });
});

const dialog = document.querySelector("#solutionDialog");
function openSolution(id) {
  const item = solutions.find(solution => solution.id === Number(id));
  if (!item) return;
  const estimate = solutionEstimates[item.id];
  document.querySelector("#dialogIndex").textContent = String(item.id).padStart(2, "0");
  document.querySelector("#dialogCategory").textContent = item.categoryName;
  document.querySelector("#dialogTitle").textContent = item.title;
  document.querySelector("#dialogLead").textContent = item.lead;
  document.querySelector("#dialogProblems").innerHTML = item.problems.map(text => `<li>${text}</li>`).join("");
  document.querySelector("#dialogHow").innerHTML = item.how.map(text => `<li>${text}</li>`).join("");
  document.querySelector("#dialogEffect").textContent = item.effect;
  document.querySelector("#dialogDuration").textContent = estimate.duration;
  document.querySelector("#dialogTeamSize").textContent = estimate.teamSize;
  document.querySelector("#dialogBudget").textContent = estimate.budget;
  document.querySelector("#dialogTech").innerHTML = estimate.tech.map(text => `<li>${text}</li>`).join("");
  document.querySelector("#dialogTeam").textContent = estimate.team;
  document.querySelector("#dialogMetrics").innerHTML = estimate.metrics.map(metric => `<article><strong>${metric.value}</strong><span>${metric.label}</span></article>`).join("");
  dialog.showModal();
}

solutionsGrid.addEventListener("click", event => {
  const card = event.target.closest(".solution-card");
  if (card) openSolution(card.dataset.id);
});
solutionsGrid.addEventListener("keydown", event => {
  if (event.key === "Enter" || event.key === " ") {
    const card = event.target.closest(".solution-card");
    if (card) { event.preventDefault(); openSolution(card.dataset.id); }
  }
});
document.querySelector(".dialog-close").addEventListener("click", () => dialog.close());
dialog.addEventListener("click", event => {
  const rect = dialog.getBoundingClientRect();
  const outside = event.clientX < rect.left || event.clientX > rect.right || event.clientY < rect.top || event.clientY > rect.bottom;
  if (outside) dialog.close();
});

const pushContent = {
  incident: ["Мы уже решаем проблему", "В вашем регионе наблюдается ограничение мобильного интернета. Восстановление — до 18:00. Звонить в 611 не требуется.", "Компенсация будет начислена автоматически."],
  sla: ["По заявке требуется больше времени", "Приносим извинения за ожидание. Мы продолжаем работу, повторное обращение в 611 не требуется.", "Новый срок решения — сегодня до 20:00."],
  service: ["Проверьте подключённые услуги", "На номере есть платные услуги, не включённые в тариф. Управлять ими можно самостоятельно в приложении.", "Показать услуги и способы отключения →"]
};

document.querySelectorAll(".push-tabs button").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".push-tabs button").forEach(item => item.classList.remove("active"));
    button.classList.add("active");
    const [title, text, note] = pushContent[button.dataset.push];
    const message = document.querySelector("#pushMessage");
    message.animate([{ opacity: .25, transform: "translateY(4px)" }, { opacity: 1, transform: "translateY(0)" }], { duration: 220 });
    message.innerHTML = `<strong>${title}</strong><p>${text}</p><span>${note}</span>`;
  });
});

const mapData = {
  internet: { calls: "18 420", repeat: "14.7%", incidents: "12", notified: "64%" },
  voice: { calls: "9 140", repeat: "8.9%", incidents: "5", notified: "78%" },
  repeat: { calls: "2 708", repeat: "18.2%", incidents: "7", notified: "41%" },
  services: { calls: "4 820", repeat: "10.6%", incidents: "2", notified: "82%" }
};

document.querySelectorAll(".map-filter").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".map-filter").forEach(item => item.classList.remove("active"));
    button.classList.add("active");
    const values = mapData[button.dataset.map];
    Object.entries(values).forEach(([key, value]) => {
      const element = document.querySelector(`#metric${key.charAt(0).toUpperCase()}${key.slice(1)}`);
      element.animate([{ opacity: .2 }, { opacity: 1 }], { duration: 220 });
      element.textContent = value;
    });
  });
});

document.querySelectorAll(".period-switch button").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".period-switch button").forEach(item => item.classList.remove("active"));
    button.classList.add("active");
  });
});

const regions = {
  "hs-west": ["ЗАПАД · КЛАСТЕР 02", "РОСТ", "924", "12.1%", "76", "1", "Скачок обращений по голосовой связи"],
  "hs-north": ["СЕВЕР · КЛАСТЕР 07", "НОРМА", "486", "8.4%", "84", "0", "Показатели в пределах нормы"],
  "hs-center": ["ЦЕНТР · КЛАСТЕР 11", "РОСТ", "1 126", "13.6%", "78", "2", "Рост обращений по статусу заявок"],
  "hs-south": ["АЛМАТЫ · КЛАСТЕР 04", "КРИТИЧНО", "1 842", "18.2%", "72", "3", "Деградация мобильного интернета"],
  "hs-east": ["ВОСТОК · КЛАСТЕР 09", "НОРМА", "512", "9.1%", "82", "0", "Показатели в пределах нормы"]
};

function selectRegion(hotspot) {
  document.querySelectorAll(".hotspot").forEach(item => item.classList.remove("active"));
  hotspot.classList.add("active");
  const className = [...hotspot.classList].find(name => name.startsWith("hs-"));
  const [name, severity, calls, repeat, csi, incidents, reason] = regions[className];
  const card = document.querySelector("#regionCard");
  card.animate([{ opacity: .25, transform: "translateY(5px)" }, { opacity: 1, transform: "translateY(0)" }], { duration: 220 });
  card.innerHTML = `<div><span>${name}</span><b class="severity">${severity}</b></div><strong>${calls} <small>обращения / 24ч</small></strong><dl><div><dt>Повторка</dt><dd>${repeat}</dd></div><div><dt>CSI</dt><dd>${csi}</dd></div><div><dt>Инциденты</dt><dd>${incidents}</dd></div></dl><p><i></i> Основная причина: ${reason}</p>`;
}

document.querySelectorAll(".hotspot").forEach(hotspot => {
  hotspot.addEventListener("click", () => selectRegion(hotspot));
  hotspot.addEventListener("keydown", event => {
    if (event.key === "Enter" || event.key === " ") { event.preventDefault(); selectRegion(hotspot); }
  });
});

const heatLevelLabels = { critical: "КРИТИЧНО", high: "ВЫСОКИЙ УРОВЕНЬ", medium: "ТРЕБУЕТ ВНИМАНИЯ", low: "В ПРЕДЕЛАХ НОРМЫ" };
const heatRepeat = { critical: "18.2%", high: "14.6%", medium: "11.8%", low: "8.4%" };

function selectHeatRegion(region) {
  document.querySelectorAll(".heat-region").forEach(item => item.classList.remove("active"));
  region.classList.add("active");
  const level = ["critical", "high", "medium", "low"].find(name => region.classList.contains(`heat-${name}`)) || "low";
  const name = region.dataset.region;
  const complaints = Number(region.dataset.complaints).toLocaleString("ru-RU");
  const card = document.querySelector("#regionCard");
  card.animate([{ opacity: .25, transform: "translateY(5px)" }, { opacity: 1, transform: "translateY(0)" }], { duration: 220 });
  card.innerHTML = `<div><span>${name}</span><b class="severity">${heatLevelLabels[level]}</b></div><strong>${complaints} <small>жалоб / 7 дней</small></strong><dl><div><dt>Повторка</dt><dd>${heatRepeat[level]}</dd></div><div><dt>Связь</dt><dd>${level === "critical" ? "42%" : "31%"}</dd></div><div><dt>Интернет</dt><dd>${level === "critical" ? "58%" : "69%"}</dd></div></dl><p><i></i> Пример агрегации по территории без показа персональных данных</p>`;
}

document.querySelectorAll(".heat-region").forEach(region => {
  region.addEventListener("mouseenter", () => selectHeatRegion(region));
  region.addEventListener("focus", () => selectHeatRegion(region));
  region.addEventListener("click", () => selectHeatRegion(region));
});

document.querySelectorAll(".complaint-point").forEach(point => {
  point.addEventListener("click", () => {
    const card = document.querySelector("#regionCard");
    card.innerHTML = `<div><span>${point.dataset.place}</span><b class="severity">КРАСНАЯ ЗОНА</b></div><strong>${point.dataset.value} <small>жалоб / 7 дней</small></strong><dl><div><dt>Повторка</dt><dd>17.4%</dd></div><div><dt>Связь</dt><dd>39%</dd></div><div><dt>Интернет</dt><dd>61%</dd></div></dl><p><i></i> Пример детализации до города или населённого пункта</p>`;
  });
});

let afterModernization = false;
document.querySelector("#beforeAfter").addEventListener("click", event => {
  afterModernization = !afterModernization;
  event.currentTarget.textContent = afterModernization ? "После модернизации" : "До модернизации";
  document.querySelector("#metricRepeat").textContent = afterModernization ? "8.8%" : "14.7%";
  document.querySelector("#metricIncidents").textContent = afterModernization ? "5" : "12";
  document.querySelector(".interactive-map").classList.toggle("after-mode", afterModernization);
});

const revealObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add("visible");
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: .1, rootMargin: "0px 0px -40px" });
document.querySelectorAll(".reveal").forEach(element => revealObserver.observe(element));

const counterObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (!entry.isIntersecting) return;
    const target = Number(entry.target.dataset.counter);
    const duration = 800;
    const start = performance.now();
    function tick(now) {
      const progress = Math.min((now - start) / duration, 1);
      entry.target.textContent = Math.round(target * (1 - Math.pow(1 - progress, 3))).toLocaleString("ru-RU");
      if (progress < 1) requestAnimationFrame(tick);
    }
    requestAnimationFrame(tick);
    counterObserver.unobserve(entry.target);
  });
}, { threshold: .5 });
document.querySelectorAll("[data-counter]").forEach(element => counterObserver.observe(element));

const menuToggle = document.querySelector(".menu-toggle");
const mainNav = document.querySelector(".main-nav");
menuToggle.addEventListener("click", () => {
  const open = mainNav.classList.toggle("open");
  menuToggle.setAttribute("aria-expanded", String(open));
});
mainNav.querySelectorAll("a").forEach(link => link.addEventListener("click", () => {
  mainNav.classList.remove("open");
  menuToggle.setAttribute("aria-expanded", "false");
}));

const sections = [...document.querySelectorAll("main section[id]")];
const navLinks = [...document.querySelectorAll(".main-nav a")];
const navObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (!entry.isIntersecting) return;
    navLinks.forEach(link => link.classList.toggle("active", link.getAttribute("href") === `#${entry.target.id}`));
  });
}, { rootMargin: "-25% 0px -65%", threshold: 0 });
sections.forEach(section => navObserver.observe(section));

document.querySelector("#printButton")?.addEventListener("click", () => window.print());
