# HESBA (حِسبة) — UX Design Specification

**Purpose:** UX handoff specification for the HESBA financial intelligence platform  
**Primary source:** HESBA Project Overview PDF (five pages, Arabic)  
**Scope:** Product experience, information architecture, user flows, low-fidelity screen structure, interaction principles, and trust requirements. No implementation or visual styling specification.

## How to read this document

- **PDF requirement** identifies a capability or direction explicitly described in the project overview.
- **UX recommendation** describes a proposed way to make that capability understandable and usable. It is not a confirmed product rule.
- **Open question** identifies a decision the product team must make before detailed interaction or visual design.
- Personas are audience archetypes derived from the product scope, not findings from interviews or other user research.

## 1. Product UX analysis

### Core value

HESBA brings day-to-day financial records, cash-flow forecasts, and financial decision comparisons into one platform. Its core promise is to help users move beyond understanding where money went and consider what may happen if they make a different financial decision.

The product has one shared financial foundation with different experiences and permissions:

| Experience | PDF-defined scope | Roadmap |
|---|---|---|
| Personal | Income and expenses; debts and installments; financial goals; flexible budgets; cash-flow forecasting; financial decision simulation | Phase 1 |
| Family | Shared household budgets; allocation of obligations; shared savings goals; member permissions and privacy | Phase 2 |
| Business | Sales, purchases, and expenses; customer and supplier debts; profitability and cash-flow monitoring; shortage warnings | Phase 3 |
| Enterprise | Integrations and advanced automation | Phase 4 |

### User needs

1. Understand current financial activity, upcoming commitments, and available cash in plain language.
2. Anticipate how income timing, expenses, and obligations may affect future liquidity.
3. Compare financial options before making a consequential decision.
4. Adjust a budget to reflect a changing situation and understand the effect before confirming the change.
5. Tell confirmed historical information apart from assumptions, estimates, and projections.
6. Review information derived from financial documents before it is accepted as accurate.
7. Revisit past expectations and compare them with actual outcomes.
8. In family and business contexts, see the information relevant to the user’s role without obscuring ownership or permissions.

### Main usability challenges

- A forecast can be mistaken for a guaranteed outcome if uncertainty, assumptions, and data quality are hidden.
- Incomplete or inconsistent financial data can make comparisons unhelpful or misleading.
- Debts, installments, obligations, and actual payments are related concepts that should not be conflated in the interface.
- Scenario comparisons can overload users if too many metrics or assumptions are shown at once.
- Family sharing requires understandable permissions and privacy boundaries.
- Business profitability and cash availability are different concepts; the interface must not imply that sales or profit are cash on hand.
- Arabic is the primary language. Layout, navigation, dates, currency, charts, and mixed Arabic/Latin content need deliberate RTL handling.

### Problems HESBA addresses

The PDF presents HESBA as a way to organize transactions, anticipate liquidity, compare financial choices, plan for irregular income, manage obligations, identify possible shortages, and learn by comparing predictions with later results. It positions the product as a decision-support tool, not simply a transaction list or a decorative dashboard.

## 2. Information architecture

### Phase 1 — Personal

```text
HESBA
├── Access
│   ├── Register
│   └── Sign in
├── Personal workspace
│   ├── Dashboard
│   │   ├── Current financial overview
│   │   ├── Upcoming obligations
│   │   └── Cash-flow outlook / possible shortage
│   ├── Transactions
│   │   ├── Income
│   │   ├── Expenses
│   │   └── Transaction details / linked document
│   ├── Budgets
│   │   ├── Budget overview
│   │   ├── Category allocations
│   │   └── Actual spending and proposed adjustments
│   ├── Goals
│   │   └── Personal financial goals
│   ├── Debts & obligations
│   │   ├── Debts
│   │   ├── Installments / payment plans
│   │   └── Upcoming payments
│   ├── Cash flow
│   │   ├── Forecast
│   │   ├── Assumptions and data quality
│   │   └── Possible shortage
│   ├── Decision simulator
│   │   ├── Decision details
│   │   ├── Scenario comparison
│   │   └── Confirmation / decision status
│   ├── Decision history
│   │   └── Predicted and actual outcomes
│   ├── Documents
│   │   ├── Uploaded documents
│   │   └── Review and confirm extracted information
│   └── Settings / profile
└── Workspace selection (recommended if multiple workspaces are available)
```

### Phase 2 — Family

```text
Family workspace
├── Shared overview
├── Shared budget
├── Obligations
│   └── Allocation among members
├── Shared savings goals
└── Members & access
    ├── Member permissions
    └── Privacy controls
```

The PDF requires shared budgets, obligation distribution, shared goals, permissions, and privacy. It does not define family roles, record visibility, or approval rules.

### Phase 3 — Business

```text
Business workspace
├── Business overview
├── Sales
├── Purchases
├── Expenses
├── Customers
│   └── Customer debts
├── Suppliers
│   └── Supplier debts
├── Profitability
├── Cash flow
└── Shortage warnings
```

### Phase 4 — Enterprise

Integrations and advanced automation are roadmap items. Specific integrations and automations are not defined in the PDF and should not be designed as confirmed capabilities.

### Navigation recommendation

For the Personal MVP, keep Dashboard, Transactions, Budgets, Cash flow, Decision simulator, and Debts & obligations in stable primary navigation. Keep Goals and Decision history easy to reach in the same financial navigation group. Documents should be reachable both from a document list and from the financial record they support. Always identify the current workspace.

## 3. User personas

These are product-use archetypes based on the PDF scope, not research-backed demographic profiles.

### Personal finance planner — irregular income

- **Goals:** understand what is safe to spend, plan around obligations, and compare options before committing.
- **Needs:** clear estimates, visible assumptions, and an understandable way to account for changing income.
- **Challenges:** a fixed-income assumption may not represent their situation; a forecast may appear more certain than its inputs justify.
- **HESBA relevance:** irregular-income planning, liquidity forecasts, possible-shortage planning, and decision comparisons.

### Household financial coordinator

- **Goals:** understand shared household commitments and how obligations are distributed.
- **Needs:** a shared financial view with clear privacy and access boundaries.
- **Challenges:** uncertainty about what each member can see or change.
- **HESBA relevance:** family budgets, obligation allocation, shared goals, permissions, and privacy.
- **Caveat:** “coordinator” is a persona framing only; the PDF does not define family roles.

### Business finance decision maker

- **Goals:** understand business cash flow, profitability, and customer/supplier obligations; identify possible shortages.
- **Needs:** a clear view of business activity and its cash-flow implications.
- **Challenges:** confusing sales or profit with available cash; overlooking payment timing.
- **HESBA relevance:** business records, profitability analysis, cash-flow monitoring, and shortage warnings.
- **Caveat:** business size, accounting policy, and operating roles are unspecified.

## 4. Core user flows

The flows use recommended interaction details where the PDF does not prescribe a precise sequence. Data fields, validation rules, thresholds, and external services must be confirmed before implementation.

### 4.1 First-time registration and onboarding

1. **Start:** user opens HESBA.
2. **Action:** choose Register or Sign in.
3. **System:** present the access form and explain the next step.
4. **Decision:** new or returning user.
5. **System:** for a new user, open Personal workspace setup as the Phase 1 starting experience.
6. **Possible errors:** missing/invalid required input, existing account, or access failure.
7. **Outcome:** user reaches initial financial setup.

**Open questions:** supported sign-in methods, identity requirements, recovery flow, and required consent.

### 4.2 Set up an initial financial profile

1. **Start:** user enters the Personal experience for the first time.
2. **Action:** provide the financial context requested by HESBA, such as income pattern, available cash, or known obligations if these are required by the agreed forecast.
3. **System:** explain why each input matters and identify incomplete information.
4. **Decision:** fixed or variable income; enter now or skip an optional item.
5. **Possible errors:** invalid amount/date or contradictory information.
6. **Outcome:** a preliminary financial picture is available, with missing inputs clearly identified.

**Open questions:** required profile fields, whether an opening balance is necessary, and which details can be skipped.

### 4.3 Add income or an expense

1. **Start:** Dashboard or Transactions.
2. **Action:** select income or expense, enter required details, and review.
3. **System:** show a confirmation of the entered information before saving it as a confirmed transaction.
4. **Decision:** manual entry or document-assisted path, if document extraction is available.
5. **Possible errors:** missing/invalid information, suspected duplicate, or unreadable document.
6. **Outcome:** confirmed transaction appears in the history and relevant financial views.

The PDF describes manual entry or information from financial documents and emphasizes user review. It does not confirm an OCR/AI service or bank connection.

### 4.4 Create and manage a budget

1. **Start:** Budgets or a relevant Dashboard prompt.
2. **Action:** create a budget and set allocations.
3. **System:** show planned amounts alongside actual spending when available.
4. **Decision:** select or revise allocations.
5. **Possible errors:** incomplete amounts or insufficient transaction history for a meaningful comparison.
6. **Outcome:** user can review budget versus actual spending and approve an adjustment.

The PDF says budgets should adapt to real circumstances and that proposed differences should be explained before approval.

**Open questions:** period definitions, categories, rollover behavior, and whether multiple budgets can coexist.

### 4.5 Review a cash-flow forecast

1. **Start:** Cash flow or forecast summary on Dashboard.
2. **Action:** open a forecast period.
3. **System:** show expected cash movement, upcoming obligations, and any possible-shortage indicator.
4. **Decision:** inspect assumptions or missing data before relying on the result.
5. **Possible errors:** insufficient/inconsistent data or unconfirmed amounts/dates.
6. **Outcome:** user understands the outlook and its contributing information.

**UX requirement:** distinguish projected values from confirmed transaction history and disclose the period, assumptions, data quality, and uncertainty.

### 4.6 Simulate a financial decision

1. **Start:** Decision simulator or a relevant debt/transaction context.
2. **Action:** select a decision to compare and enter its details.
3. **System:** check completeness and show a baseline alongside available options.
4. **Decision:** adjust assumptions, add an alternative, or continue with the comparison.
5. **Comparison:** explain expected liquidity, relevant obligations, financial consequences, changed inputs, and estimated values.
6. **Possible errors:** missing inputs, incomparable scenarios, or incomplete underlying data.
7. **Outcome:** user makes an informed choice or leaves the scenario unexecuted.

**Critical separation:** saving a scenario is not the same as executing the decision or creating a confirmed transaction. Require an explicit confirmation for the user’s chosen decision.

### 4.7 Identify and respond to a possible cash shortage

1. **Start:** forecast or shortage indicator.
2. **Action:** open the warning and review contributing items.
3. **System:** explain the projected shortfall and show comparable alternatives if supported.
4. **Decision:** inspect source data, compare an alternative, adjust a plan, or take no action.
5. **Possible errors:** warning relies on incomplete data or estimated dates/amounts.
6. **Outcome:** user understands the risk and may approve a revised plan.

**UX recommendation:** avoid alarmist or mandatory language; show what changed and what remains uncertain.

### 4.8 Manage debts and installments

1. **Start:** Debts & obligations or an upcoming payment.
2. **Action:** review or enter a debt, installment, or proposed payment plan.
3. **System:** show payment timing and compare effects of alternative repayment plans on liquidity and cost.
4. **Decision:** compare plans, confirm details, or leave unchanged.
5. **Possible errors:** missing amount/date or unreviewed/conflicting document information.
6. **Outcome:** an existing obligation remains distinguishable from a planned alternative.

### 4.9 Review past decisions and actual outcomes

1. **Start:** Decision history.
2. **Action:** open a prior decision and compare forecast with actual outcome.
3. **System:** show the original expectation, outcome data, and difference.
4. **Decision:** determine whether actual data is complete enough for a comparison.
5. **Possible errors:** actual results missing, incomplete, or not comparable with the original prediction.
6. **Outcome:** user reviews the result and learns what changed.

Do not label a result “wrong” solely because it differs from a forecast. Explain known differences and avoid inventing a cause when it is unknown.

## 5. Low-fidelity UX wireframes

Wireframes are structural and are not high-fidelity visual designs. Proposed Arabic labels should be validated for natural product terminology. On desktop, primary navigation is on the right; on mobile, retain RTL reading order and provide clearly labeled navigation.

### 5.1 Login / registration

```text
┌──────────────────────────────────────────┐
│ حِسبة                         العربية   │
│                                          │
│        افهم وضعك. اختر قرارك.            │
│                                          │
│                 [تسجيل الدخول]          │
│            البريد / وسيلة الدخول*        │
│                 [________________]       │
│            كلمة المرور*                  │
│                 [________________]       │
│               [متابعة]                   │
│        مستخدم جديد؟ [إنشاء حساب]          │
└──────────────────────────────────────────┘
```

- **Purpose:** access the product.
- **Primary action:** continue.
- **Secondary action:** switch between sign-in and registration.
- **States:** validation error, loading, success, recoverable failure.
- **Open question:** supported access methods and account recovery.

### 5.2 Onboarding / initial setup

```text
┌──────────────┬───────────────────────────┐
│ الخطوات      │ إعداد وضعك المالي         │
│ ١. الأساسيات │ لماذا نطلب هذه المعلومة؟  │
│ ٢. الدخل     │ الدخل: [منتظم / متغير]    │
│ ٣. الالتزامات│ المبلغ / التاريخ: [____]   │
│ ٤. المراجعة  │ المتاح حالياً: [________]  │
│              │ الالتزامات: [إضافة]       │
│              │ [حفظ ومتابعة] [تخطي*]     │
└──────────────┴───────────────────────────┘
```

- **Purpose:** gather the context needed for an initial financial picture.
- **Primary action:** save and continue.
- **Secondary action:** skip an optional item, only if the product allows it.
- **States:** incomplete, invalid, saved, or blocked by a required field.
- **Open question:** which fields and steps are truly required.

### 5.3 Personal dashboard

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ ملخصك المالي                     │
│ الرئيسية      │ المتاح حالياً*  الالتزامات القادمة│
│ المعاملات     │ [قيمة]            [قيمة]          │
│ الميزانية     │                                  │
│ التدفق النقدي │ توقع السيولة                     │
│ المحاكي       │ [رسم/خط زمني مع وسيلة شرح]        │
│ الديون        │                                  │
│ الأهداف       │ تنبيه: احتمال عجز [التفاصيل]      │
│ سجل القرارات  │                                  │
│               │ [إضافة معاملة] [اختبر قراراً]      │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** summarize financial context and provide clear next actions.
- **Primary actions:** add a transaction or open the simulator.
- **Secondary actions:** review obligations, budget, or forecast.
- **States:** empty setup, current overview, possible-shortage warning, incomplete-data explanation.
- **Trust:** label projected amounts and do not rely on a chart without a plain-language explanation.

### 5.4 Transactions

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ المعاملات                        │
│               │ [كلها] [دخل] [مصروفات] [تصفية]   │
│               │ [بحث/فترة]                        │
│               │ التاريخ | الوصف | النوع | المبلغ  │
│               │ -------------------------------- │
│               │ ...                              │
│               │ [إضافة دخل] [إضافة مصروف]        │
│               │ مستند مرتبط: [عرض / مراجعة]      │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** review and enter confirmed income and expenses.
- **Primary actions:** add income or expense.
- **Secondary actions:** filter, inspect details, review linked document.
- **States:** empty, loading, saved, validation error, possible duplicate, unreviewed document details.
- **Responsive recommendation:** use labeled transaction cards on narrow screens instead of forcing dense horizontal scrolling.

### 5.5 Budget management

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ الميزانية                        │
│               │ الفترة: [اختيار]                 │
│               │ المخصص | الفعلي | المتبقي         │
│               │ -------------------------------- │
│               │ [فئة]  [مبلغ]  [مبلغ]  [مبلغ]    │
│               │ ...                              │
│               │ تعديل مقترح [السبب والأثر]        │
│               │ [مراجعة التعديل] [تأكيد]          │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** compare planned allocations with actual spending.
- **Primary action:** create or edit a budget.
- **Secondary action:** inspect a proposed adjustment.
- **States:** no budget, incomplete actual data, approaching/exceeding allocation (thresholds TBD), proposed change awaiting approval.
- **Trust:** planned and actual amounts are distinct; a budget is not a transaction.

### 5.6 Cash-flow forecast

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ توقع التدفق النقدي               │
│               │ الفترة: [اختيار]                  │
│               │ [متوقع — ليس رصيداً مؤكداً]       │
│               │ [خط زمني / رسم مع قيم وتسميات]    │
│               │ الالتزامات المؤثرة [قائمة]        │
│               │ الافتراضات ومصدر البيانات [عرض]   │
│               │ جودة البيانات / الثقة [شرح]       │
│               │ احتمال عجز [التفاصيل]             │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** explain expected liquidity and possible shortages.
- **Primary action:** inspect the forecast and assumptions.
- **Secondary action:** review contributing transactions or obligations.
- **States:** forecast ready, insufficient data, stale inputs, possible shortage, unavailable.
- **Trust:** define the horizon and confidence before presenting them; never style a projected balance as confirmed cash.

### 5.7 Decision simulator

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ اختبر قراراً                     │
│               │ القرار: [اختيار / وصف]            │
│               │ التفاصيل: [المبلغ] [الموعد]       │
│               │ [إضافة خيار للمقارنة]             │
│               │                                  │
│               │ الأساس الحالي | الخيار أ | الخيار ب│
│               │ السيولة المتوقعة                 │
│               │ الالتزامات                       │
│               │ التكلفة / الأثر المالي            │
│               │ الافتراضات [عرض]                  │
│               │ [حفظ المقارنة] [اعتماد القرار]    │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** compare financial consequences before committing.
- **Primary action:** create or compare scenarios.
- **Secondary action:** change an input or inspect an assumption.
- **States:** draft, incomplete inputs, comparable, incomparable, awaiting confirmation, executed/awaiting outcome.
- **Trust:** show a baseline and the inputs that differ; saving a scenario must not create an actual transaction.
- **Progressive disclosure:** show the outcome summary first, then allow inspection of assumptions and detailed contributing figures.

### 5.8 Debts and obligations

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ الديون والالتزامات               │
│               │ [قائمة الالتزامات القادمة]        │
│               │ الجهة | المبلغ | موعد الدفع       │
│               │ -------------------------------- │
│               │ [تفاصيل الدين]                   │
│               │ خطة السداد الحالية               │
│               │ مقارنة أثر خطة بديلة              │
│               │ على السيولة والتكلفة               │
│               │ [مراجعة الخطة] [تأكيد]             │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** inspect debts and scheduled payments and compare repayment plans.
- **Primary action:** review a debt or plan.
- **Secondary action:** compare an alternative or inspect a supporting document.
- **States:** empty, missing details, document awaiting review, plan comparison, confirmed commitment.
- **Trust:** distinguish existing obligation from proposed repayment plan.

### 5.9 Decision history

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ سجل القرارات                     │
│               │ القرار | التاريخ | الحالة         │
│               │ -------------------------------- │
│               │ [فتح القرار]                     │
│               │ المتوقع: [ملخص]                  │
│               │ الفعلي: [ملخص / لم يسجل بعد]      │
│               │ الفرق: [شرح ما تغير]              │
│               │ الافتراضات الأصلية [عرض]          │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** review previous expectations and compare them with outcomes.
- **Primary action:** open a previous decision.
- **Secondary action:** review actual outcome data if that workflow is supported.
- **States:** empty, forecast only, outcome available, incomplete comparison.
- **Trust:** avoid implying that a forecast is a promise or that any variance is the user’s fault.

### 5.10 Settings / profile

```text
┌───────────────┬──────────────────────────────────┐
│ التنقل        │ الإعدادات                        │
│               │ الملف الشخصي                     │
│               │ مساحة العمل الحالية              │
│               │ الوصول والخصوصية*                 │
│               │ اللغة / تنسيق الأرقام*             │
│               │ [حفظ]                             │
└───────────────┴──────────────────────────────────┘
```

- **Purpose:** access essential account and workspace controls.
- **Primary action:** edit an available setting.
- **Secondary action:** review workspace/privacy information.
- **States:** saved, unsaved changes, validation error.
- **Open question:** settings scope is not specified in the PDF; do not imply unconfirmed options.

## 6. Interaction design

### Forms

- Keep forms short and progressively disclose optional detail.
- Keep currency and date context visible during financial entry.
- Explain why a forecast-relevant field is requested.
- Show validation beside the affected field; preserve other entered information on error.
- Provide a review step before saving a consequential change.

### Financial lists, filters, and charts

- Label transaction date, description, type, and amount in text; do not rely on icons or color alone.
- Make active filters visible and provide an obvious way to clear them.
- Label chart values, units, and time period, and provide a textual summary and a non-chart way to inspect values.
- On small screens, prioritize legible labeled cards over dense tables.

### Alerts and warnings

- State what may happen, when it may happen, and which inputs contribute.
- Distinguish a possible shortage from a confirmed shortage.
- Explain uncertainty and provide a route to inspect contributing data.
- Do not establish alert thresholds, delivery channels, or automatic actions until product rules are defined.

### Scenario comparison

- Show baseline and alternatives side by side where space permits.
- Keep units and time periods consistent.
- Identify which assumptions or inputs differ.
- Separate current commitments from proposed changes.
- Require explicit user confirmation before treating a choice as executed.

### Document review

- Show proposed extracted values for review and confirmation before treating them as accepted financial data.
- Identify missing or conflicting details specifically and let the user correct them.
- Do not imply OCR/AI or any external service exists; the PDF does not establish how extraction happens.

### Shared interaction states

| State | UX response |
|---|---|
| Empty | Explain the section’s purpose and offer a relevant first action; do not fabricate financial examples. |
| Loading | Preserve context and indicate that data is being prepared; do not present a stale forecast as current. |
| Success | Confirm the saved action and where it appears. |
| Error | Explain the failure, preserve input where possible, and offer correction or retry. |
| Warning | Explain uncertainty or consequence in words, not only by color/icon. |
| Disabled | Explain what information or action is missing. |

## 7. Financial UX, trust, and accessibility

### Distinguish information states

Use persistent text labels—not color alone—to distinguish:

- **Confirmed:** a reviewed/entered record accepted into financial history.
- **Needs review:** a document-derived or otherwise unverified value.
- **Estimated / forecast:** a projection about a future period.
- **Assumption:** an input used for a forecast or scenario.
- **Actual outcome:** a value recorded after a decision or forecast period.

Never style a projected amount as a confirmed historical transaction without an explicit status label.

### Communicate uncertainty

State the forecast period and explain assumptions, data sources, freshness, and confidence in understandable language. If important information is missing, show how it limits the estimate. Avoid guaranteed-outcome language for predictions.

### Help users make informed decisions

For every scenario comparison, help the user distinguish:

1. What is true in the current record.
2. What is being tested.
3. What HESBA estimates may happen.
4. What the user chose to do.
5. What actually happened later.

### RTL and accessibility

- Use right-aligned Arabic reading order and RTL-aware navigation, forms, and comparison layouts.
- Keep currency symbols, signs, separators, and dates legible and consistent; exact conventions require confirmation.
- Do not rely on red/green alone for loss, shortage, or status.
- Provide text labels and accessible descriptions for charts and statuses.
- Keep keyboard focus order consistent with the visual reading order and use clear control labels.
- Test long Arabic labels, mixed Arabic/Latin text, numbers, and narrow layouts.

## 8. Phased design recommendation

### Phase 1 — Personal MVP

Prioritize transactions, flexible budgets, debts and installments, personal goals, cash-flow forecasts, financial decision simulation, possible-shortage visibility, and decision history. Keep forecasts and scenarios clearly separate from confirmed transaction history.

### Phase 2 — Family

Add family workspace context, shared budgets, obligation distribution, shared goals, and explicit member permissions/privacy. Finalize role and visibility rules before designing detailed member-management interactions.

### Phase 3 — Business

Add sales, purchases, expenses, customers, suppliers, customer/supplier debts, profitability, business cash flow, and shortage warnings. Confirm business terminology and accounting assumptions before detailed design.

### Phase 4 — Enterprise

Keep integrations and advanced automation out of earlier-phase navigation and UX until specific capabilities and policies are defined.

## 9. Open questions for product clarification

1. Which sign-in methods, identity fields, recovery, and consent steps are required?
2. Which personal financial-profile inputs are mandatory? Is an opening cash balance required?
3. Which currencies, number/date formats, calendars, and time zones must be supported?
4. Which transaction fields and categories are required? Are recurring transactions in scope?
5. Which document types are supported, and how is information extracted? Is extraction automatic or user-entered?
6. What budget periods, default categories, rollover rules, and multiple-budget behavior are intended?
7. Which debt types and repayment structures must the first release represent?
8. What forecast horizons, confidence definitions, freshness expectations, and shortage criteria are intended?
9. Which decision types and financial measures are supported by the initial simulator?
10. What counts as an executed decision, and how is the actual outcome recorded?
11. Which family roles and record-visibility/privacy rules apply? Who can edit or approve shared records?
12. What business types, sales/purchase details, customer/supplier debt workflows, and profitability definitions are in scope?
13. How should shortage warnings be triggered, revisited, and dismissed?
14. Which integrations and automations are planned for Phase 4?

## Source boundary

The PDF is the source for product experiences, roadmap phases, and the major capabilities summarized here. Specific authentication, data-entry fields, forecasting formulas, thresholds, integrations, access policies, and detailed screen behavior remain product decisions. Recommendations in this document should be validated before being treated as requirements.
