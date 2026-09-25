# 检索与统计方法

> 本手册的文献检索、纳入与数字核对方法说明。编写时间: 2026-09-25。

## 1. 数据源

所有文献通过 Europe PMC REST API 检索与调取
(`https://www.ebi.ac.uk/europepmc/webservices/rest/search`), 限定 `SRC:MED`
(MEDLINE 收录), 使用 `resultType=core` 返回结构化摘要全文。

## 2. 检索策略

共 11 轮、约 100 组查询, 覆盖以下主题面 (每组查询给出代表式, 实际组合略有变体):

| 主题面 | 代表检索式 |
|---|---|
| 牙周病与死亡/心血管 | `TITLE:(periodont*) AND TITLE:(mortality)`; `TITLE:(edentulism)` |
| 刷牙行为与大人群队列 | `TITLE:(toothbrushing) AND TITLE:(mortality)` |
| 血压/糖尿病的因果与治疗 | `TITLE:(periodontal) AND TITLE:(hypertension)`; MR 与 RCT 分检 |
| 痴呆/认知 | `TITLE:(tooth loss) AND TITLE:(dementia)` 及病原学 (P. gingivalis) |
| 电动牙刷/含氟牙膏/水氟 | Cochrane 专检: `TITLE:("fluoride toothpaste")` 等 |
| 糖/酸蚀/口香糖 | `TITLE:(sugar) AND TITLE:(caries)`; `TITLE:(erosion)` |
| 叩齿与咬硬物 (专项) | tooth tapping / tooth percussion / occlusal exercise / 叩齿 等穷尽组合 |
| 咬合创伤/磨牙症/颈部缺损 | `TITLE:(occlusal trauma)`; `TITLE:(bruxism)`; abfraction |
| 遗传度 | `TITLE:(heritability) AND TITLE:(periodontal OR caries)`; 双生子研究 |
| 中国流调 | `TITLE:(China) AND TITLE:(periodontal)`; 第四次全国口腔健康流调 |
| 扩展面 (二轮) | 早产 / 槟榔 / HPV / GERD / 勃起功能障碍 / 营养 / 种植体周炎 / 口干 / 牙龈退缩 / 木糖醇 / 牙科恐惧 / 冠周炎 |

**排序与收紧**: 默认按被引量降序 (`CITED desc`), 发现易被"引用一切的巨型综述"
(AHA 统计声明, GBD 全球负担) 污染后, 对主题面加 `TITLE:(...)` 收紧到标题级;
Cochrane 系统综述用精确标题短语命中 (期刊字段查询不稳定)。

**负结果判定** (叩齿专项): 英文关键词 (tapping/percussion/exercise×tooth/teeth/jaw)
与中文关键词 (叩齿) 穷尽组合后, 命中文献均为口腔神经反射研究、根管叩诊诊断或磨牙症
文献, 无一为"叩齿保健"对照试验 — 记为证据真空而非检索失败 (检索式与命中说明见 evidence/T29.md)。

## 3. 纳入与数字核对

1. 每轮检索筛出候选 PMID (按被引量、期刊、年份与主题相关性人工判断), 合计约百篇;
2. 逐篇调取摘要原文, 手册中出现的每一个统计数字 (RR/HR/OR/CI/MD/SMD/P/患病率)
   均与摘要原文逐字比对后方可写入; 摘要截断处的数字标注"见原文", 不凭记忆补全;
3. 同一数字多处出现时 (README/topics/evidence 三层), 以 evidence 条目为准, 上层引用回链;
4. 派生表述 (如"降 40%") 必须能从摘要原始数字直接换算。

## 4. 证据分级与来源质量评分

每个条目按研究设计标注证据等级: RCT > 队列/meta > 横断面 > 综述/机制 > 体外/动物。

期刊与课题组评分 (本手册内部参考标准, 供读者权衡来源可靠性):

| 分档 | 期刊/来源 | 本手册命中代表 |
|---|---|---|
| A (顶刊/权威指南) | NEJM, Lancet, Lancet Oncol, Lancet Healthy Longevity; Cochrane Library; JAMA 系 | NEJM 孕期牙周治疗 RCT (T31); Cochrane 含氟牙膏/水氟/牙线 (T15/T20); Lancet HPV 口咽癌双 RCT (T44); Lancet Oncol 槟榔负担 (T32) |
| A- (领域旗舰刊) | J Clin Periodontol, J Dent Res, Periodontology 2000, Nature 系, Eur Heart J, Diabetes Care | EFP/WHF 共识 (T03); Eur Heart J 降压 RCT (T04); Nat Commun 龋齿 GWAS (T28); Diabetes Care 牙周-血糖 (T07) |
| B+ (高质量专科刊) | J Periodontol, J Clin Periodontol 早中期卷, Clin Oral Implants Res, Caries Res, Int J Cancer, Br J Cancer, Am J Obstet Gynecol | Michalowicz 双生子遗传度 (T28); 槟榔台湾病例对照系列 (T32) |
| B (可靠但影响中等) | J Dent, J Oral Rehabil, Am J Med, Clin Nutr, JAMDA, BMC Oral Health | 种植体周炎 meta (T37); 牙科恐惧 vicious cycle (T42) |
| C (观点/机制, 仅作机制佐证) | 叙事综述、单中心小样本、体外实验 | 酸蚀 pH 梯度体外 (T27); abfraction 批判综述 (T25) |

课题组维度 (代表性举例): Axelsson 组 (瑞典卡尔斯塔德, 30 年菌斑程序天花板, T18);
Michalowicz 组 (明尼苏达, 双生子遗传度经典系列, T28); Dominy 组 (P. gingivalis-AD 病原学,
T12); Tonetti/Hujoel 等牙周循证核心作者。同一课题组若有多篇, 本手册优先取其方法学最强的
一篇 (meta/RCT 优先于叙事综述)。

## 5. 局限性

- 摘要原文是唯一核对底本, 未逐篇读全文; 摘要未报的关键 CI 标注"见原文";
- 负结果 (证据真空) 依赖检索式覆盖面, 不能排除未索引的灰色文献 (如中文传统医学期刊);
- 观察性研究的残余混杂无法完全排除, 全部相对风险请带 95% CI 阅读;
- 期刊分档是内部参考标准, 非官方分区。
