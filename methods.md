# Methods: Search Strategy and Number Verification

> How the literature was searched, selected, and number-checked. Compiled 2026-09-25.
> 中文版见文末附录 / Chinese summary in the appendix below.

## 1. Data source

All literature was retrieved through the Europe PMC REST API
(`https://www.ebi.ac.uk/europepmc/webservices/rest/search`), restricted to `SRC:MED`
(MEDLINE-indexed), using `resultType=core` to return structured abstracts in full.

## 2. Search strategy

13 rounds and roughly 125 query groups covered the following topic facets (one
representative query string per facet; actual combinations varied slightly):

| Topic facet | Representative query |
|---|---|
| Periodontal disease & mortality/CVD | `TITLE:(periodont*) AND TITLE:(mortality)`; `TITLE:(edentulism)` |
| Toothbrushing behavior & large cohorts | `TITLE:(toothbrushing) AND TITLE:(mortality)` |
| Blood pressure / diabetes causality & treatment | `TITLE:(periodontal) AND TITLE:(hypertension)`; MR and RCT searched separately |
| Dementia / cognition | `TITLE:(tooth loss) AND TITLE:(dementia)` plus pathogen work (P. gingivalis) |
| Powered brushes / fluoride toothpaste / water fluoridation | Cochrane-focused: `TITLE:("fluoride toothpaste")` etc. |
| Sugar / erosion / chewing gum | `TITLE:(sugar) AND TITLE:(caries)`; `TITLE:(erosion)` |
| Tooth tapping & hard-food chewing (special audit) | tooth tapping / tooth percussion / occlusal exercise / 叩齿 exhaustive combinations |
| Occlusal trauma / bruxism / cervical lesions | `TITLE:(occlusal trauma)`; `TITLE:(bruxism)`; abfraction |
| Heritability | `TITLE:(heritability) AND TITLE:(periodontal OR caries)`; twin studies |
| China epidemiology | `TITLE:(China) AND TITLE:(periodontal)`; the 4th National Oral Health Survey |
| Round-2 extensions | preterm birth / betel quid / HPV / GERD / erectile dysfunction / nutrition / peri-implantitis / dry mouth / recession / xylitol / dental fear / pericoronitis |
| Round-3 extensions | sealants / fluoride varnish / orthodontic white-spot lesions / e-cigarettes / rheumatoid arthritis / chronic kidney disease / obesity / oral frailty & tongue pressure / dental radiography dosimetry / water flossers / root-caries 5,000 ppm |

**Ordering and tightening.** Default ordering was citation count descending
(`CITED desc`). After noticing contamination by "cite-everything" mega-reviews (AHA
statistical statements, GBD global-burden papers), topic facets were tightened with
`TITLE:(...)` to title-level matching; Cochrane systematic reviews were hit with exact
title phrases (journal-field queries proved unreliable).

**Negative-result determination (the tapping audit).** After exhausting English
keywords (tapping/percussion/exercise × tooth/teeth/jaw) and the Chinese keyword (叩齿),
the hits were oral neuro-reflex studies, endodontic percussion diagnostics, or bruxism
papers — none was a controlled trial of "tapping as exercise". This is recorded as an
evidence vacuum rather than a search failure (queries and hit analysis in
evidence/T29.md).

## 3. Inclusion and number verification

1. Each round produced candidate PMIDs (judged on citations, journal, year and topical
   fit), ~130 in total;
2. Every abstract was fetched, and every statistical value appearing in this handbook
   (RR/HR/OR/CI/MD/SMD/P/prevalence) was compared verbatim against the abstract before
   being written in; where an abstract truncates a value, entries mark "see original" —
   nothing is filled from memory;
3. When the same number appears at multiple levels (README/topics/evidence), the
   evidence entry is authoritative and upper layers link back;
4. Derived phrasings (e.g. "40% lower") must be directly computable from the abstract's
   original numbers.

## 4. Evidence grading and source-quality scores

Each entry is graded by study design: RCT > cohort/meta > cross-sectional >
narrative review/mechanism > in-vitro/animal.

Journal and research-group scoring (an internal reference standard for weighing source
reliability):

| Grade | Journals/sources | Handbook examples |
|---|---|---|
| A (top-tier/authoritative) | NEJM, Lancet, Lancet Oncol, Lancet Healthy Longevity; Cochrane Library; JAMA family | NEJM pregnancy periodontal-therapy RCT (T31); Cochrane fluoride toothpaste/water/floss (T15/T20); Lancet HPV-oropharyngeal twin RCTs (T44); Lancet Oncol betel-quid burden (T32) |
| A- (field flagships) | J Clin Periodontol, J Dent Res, Periodontology 2000, Nature family, Eur Heart J, Diabetes Care | EFP/WHF consensus (T03); Eur Heart J BP-lowering RCT (T04); Nat Commun caries GWAS (T28); Diabetes Care periodontal-glycemia (T07) |
| B+ (high-quality specialty) | J Periodontol, early/mid-volume J Clin Periodontol, Clin Oral Implants Res, Caries Res, Int J Cancer, Br J Cancer, Am J Obstet Gynecol | Michalowicz twin heritability (T28); Taiwan betel-quid case-control series (T32) |
| B (reliable, mid-impact) | J Dent, J Oral Rehabil, Am J Med, Clin Nutr, JAMDA, BMC Oral Health | Peri-implantitis meta (T37); dental-fear vicious cycle (T42) |
| C (opinion/mechanism, corroborative only) | Narrative reviews, small single-center samples, in-vitro work | Erosion pH gradients in vitro (T27); abfraction critical review (T25) |

Research-group dimension (examples): the Axelsson group (Karlstad, Sweden — the 30-year
plaque-control ceiling, T18); the Michalowicz group (Minnesota — the classic twin
heritability series, T28); the Dominy group (P. gingivalis-AD etiology, T12); core
evidence-based periodontology authors such as Tonetti and Hujoel. When a group has
multiple papers, the handbook prefers its methodologically strongest one (meta/RCT over
narrative review).

**Impact factors.** Journal impact factors are tagged inline as `[IF ~x]` using
approximate 2024 JCR values rounded to one decimal; the full mapping is in
[evidence/00-if-table.md](evidence/00-if-table.md). IFs serve source-weighting only —
they are not quality verdicts on individual papers.

## 5. Limitations

- Abstracts are the sole verification substrate; full texts were not read paper-by-paper;
  CIs truncated in abstracts are marked "see original";
- Negative results (evidence vacua) depend on query coverage; grey literature (e.g.
  Chinese traditional-medicine journals) outside MEDLINE cannot be excluded;
- Residual confounding in observational studies cannot be fully removed; read every
  relative risk with its 95% CI;
- Journal grading is an internal reference, not an official partition;
- IF values are approximations and drift year to year.

---

## 附录: 中文摘要 (Methods 摘要)

1. **数据源**: Europe PMC REST API, 限定 MEDLINE, `resultType=core` 取结构化摘要。
2. **检索**: 共 13 轮、约 125 组查询, 覆盖死亡/心血管、刷牙、血压/血糖、痴呆、氟化物、
   糖/酸蚀、叩齿专项、咬合创伤、遗传度、中国流调, 以及二轮 (槟榔/HPV/种植等) 与
   三轮 (窝沟封闭/涂氟/类风湿/肾病/口腔衰弱/辐射剂量等) 扩展面。默认按被引降序,
   用 `TITLE:(...)` 收紧防巨型综述污染; 叩齿穷尽检索无对照试验, 记为证据真空。
3. **核对**: 每个统计数字逐字比对摘要原文后才写入; 摘要截断处标"见原文", 不凭记忆补全;
   同一数字三层出现时以 evidence 条目为准。
4. **分级**: RCT > 队列/meta > 横断面 > 综述/机制 > 体外/动物; 期刊按 A/A-/B+/B/C
   内部分档; IF 以 `[IF ~x]` 内联标注 (2024 JCR 近似值), 仅作来源权重参考。
5. **局限**: 未逐篇读全文; 灰色文献不可排除; 观察性研究残余混杂; 分档与 IF 为内部参考。
