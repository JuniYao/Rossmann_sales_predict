# Rossmann_sales_predict


### **项目背景**

Rossmann公司在7个欧洲国家拥有超过3000家药店。Rossmann的经理的任务是提前六周预测药店的日常销售金额。药店销售额会受到包括促销、竞赛、学校和州的节假日，季节以及所在地址等等因素的影响。Rossmann的经理目前已经根据实际情况，用个人的方式进行了种种预测，由于预测方式的不同，实际准确性上有较大的区别。

为此，Rossmann公司举行了预测日常销售金额的竞赛项目。作为竞赛参与者，需要对在德国的1115家药店预测6周日常销售额。准确率高且可靠的销售预测模型可以为Rossmann公司各个药店的经理创建创建更加有效的员工日程安排，从而提高员工的劳动力与工作积极性。同时，为Rossmann建立预测模型，也可以帮助各位药店经理将重点和焦点放在如何提高客户满意度以及优化团队建设这些更加重要的方面上。

为解决此问题，需要先对历史销售数据进行探索性数据分析(EDA)，处理异常值，发现潜在结构；提取合适的特征，建立预测模型；对模型进行训练，获得模型较优参数，提高预测准确性。


### **问题陈述**

为Rossmann公司的1115家德国药店建立预测未来6周的销售的模型。该任务是一个回归预测类问题，即根据现有的历史数据：各药店历史日期中的销售、药店规模、促销方案、假期安排等等数据，进行特征分析以及预测目标分析。从历史数据合理划分训练集和验证集，使用试GBDT类模型，例如xgboost、lightgbm等模型预测未来6周的销售情况。



### **数据集和输入**

- 文档
train.csv - 包含销售的历史数据  
test.csv - 无销售的历史数据，用于输入模型后得出预测值，与实际销售比较计算准确率  
sample_submission.csv - 正确提交的数据格式  
store.csv - 关于商店的补充信息（包含商店规模、促销方案与时间等信息）

- 文档字段说明

Id - an Id that represents a (Store, Date) duple within the test set
Store - 每个药店的唯一序号
Sales - 每个已知日期的药店的周转(turnover) (目标预测值)
Customers - 已知日期的客户量
Open - 药店是否营业的标示符: 0 = 不营业, 1 = 营业
StateHoliday - 表示州假日。 通常情况下，除了少数例外，所有商店都会在州假期关闭. 所有的学校在公共假日和周末都是close的。 a = public holiday, b = Easter holiday, c = Christmas, 0 = None
SchoolHoliday - 表明（商店，日期）是否受到公立学校关闭的影响
StoreType - 区分4种不同的商店规模: a, b, c, d
Assortment - 描述了一个分类级别: a = basic, b = extra, c = extended
CompetitionDistance - 距离最近的竞争对手商店的距离
CompetitionOpenSince[Month/Year] - 距离最近的竞争对手开业的时间（月/年）
Promo - 表示当天该药店是否在进行促销活动
Promo2 - 表示一些药店持续的促销活动: 0 = 药店未参与, 1 = 药店正在参与
Promo2Since[Year/Week] - 描述商店开始参与持续促销活动的年份和日历周
PromoInterval - 描述持续促销活动，启动的连续间隔，以促销月份命名 E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

Solution Statement
(approx. 1 paragraph)

In this section, clearly describe a solution to the problem. The solution should be applicable to the project domain and appropriate for the dataset(s) or input(s) given. Additionally, describe the solution thoroughly such that it is clear that the solution is quantifiable (the solution can be expressed in mathematical or logical terms) , measurable (the solution can be measured by some metric and clearly observed), and replicable (the solution can be reproduced and occurs more than once).

Benchmark Model
(approximately 1-2 paragraphs)

In this section, provide the details for a benchmark model or result that relates to the domain, problem statement, and intended solution. Ideally, the benchmark model or result contextualizes existing methods or known information in the domain and problem given, which could then be objectively compared to the solution. Describe how the benchmark model or result is measurable (can be measured by some metric and clearly observed) with thorough detail.

Evaluation Metrics
(approx. 1-2 paragraphs)

In this section, propose at least one evaluation metric that can be used to quantify the performance of both the benchmark model and the solution model. The evaluation metric(s) you propose should be appropriate given the context of the data, the problem statement, and the intended solution. Describe how the evaluation metric(s) are derived and provide an example of their mathematical representations (if applicable). Complex evaluation metrics should be clearly defined and quantifiable (can be expressed in mathematical or logical terms).

Project Design
(approx. 1 page)

In this final section, summarize a theoretical workflow for approaching a solution given the problem. Provide thorough discussion for what strategies you may consider employing, what analysis of the data might be required before being used, or which algorithms will be considered for your implementation. The workflow and discussion that you provide should align with the qualities of the previous sections. Additionally, you are encouraged to include small visualizations, pseudocode, or diagrams to aid in describing the project design, but it is not required. The discussion should clearly outline your intended workflow of the capstone project.

Before submitting your proposal, ask yourself. . .

Does the proposal you have written follow a well-organized structure similar to that of the project template?
Is each section (particularly Solution Statement and Project Design) written in a clear, concise and specific fashion? Are there any ambiguous terms or phrases that need clarification?
Would the intended audience of your project be able to understand your proposal?
Have you properly proofread your proposal to assure there are minimal grammatical and spelling mistakes?
Are all the resources used for this project correctly cited and referenced?
