<style>
:root{
  --fg:#0f172a; --muted:#475569; --card:#f8fafc; --bd:#e2e8f0;
  --tag:#eef2ff; --tagbd:#c7d2fe; --tagfg:#1e3a8a;
}

/* Override Cayman green headings */
h1,h2,h3{ color:var(--fg) !important; font-weight:800; }
h2{ margin-top:1.6rem; }
p{ color:var(--fg); }
hr{ border:none; border-top:1px solid var(--bd); margin:1.5rem 0; }

/* ===== HERO GRID (stable) ===== */
.hero{
  display:grid;
  grid-template-columns: 180px minmax(0, 1.15fr) minmax(0, .85fr);
  gap:16px;
  padding:18px;
  border:1px solid var(--bd);
  border-radius:18px;
  background:var(--card);
  align-items:start;
}

/* IMPORTANT: allow grid children to shrink (prevents overflow) */
.hero > *{ min-width:0; }

.leftcol{ display:flex; flex-direction:column; gap:10px; align-items:flex-start; }
.mid, .right{ min-width:0; }
.right, .right *{ overflow-wrap:anywhere; word-break:break-word; }

/* Responsive */
@media (max-width: 1100px){
  .hero{ grid-template-columns: 180px 1fr; }
  .hero .right{ grid-column: 1 / -1; }
  .note-wide{ grid-column: 1 / -1; } /* full width on smaller screens */
}
@media (max-width: 720px){
  .hero{ grid-template-columns: 1fr; }
}

/* Avatar */
.avatar{
  width:160px; height:160px;
  border-radius:18px;
  object-fit:cover;
  border:1px solid var(--bd);
  background:#fff;
}
.small{ font-size:.92rem; color:var(--muted); }

/* Name block */
.h1{
  font-size:2.05rem;
  font-weight:900;
  margin:2px 0 4px;
  color:var(--fg);
  letter-spacing:.2px;
}
.subtitle{ color:var(--muted); font-size:1.05rem; margin:0 0 6px; }
.meta{ color:var(--muted); margin:6px 0 0; line-height:1.55; }

/* Buttons */
.btns{ display:flex; flex-wrap:wrap; gap:10px; margin-top:12px; }
.btn{
  display:inline-block;
  padding:8px 14px;
  border:1px solid var(--bd);
  border-radius:999px;
  background:#fff;
  color:var(--fg);
  font-size:.95rem;
  font-weight:700;
}
.btn:hover{ text-decoration:none; border-color:#cbd5e1; }

/* Tags */
.tags{ display:flex; flex-wrap:wrap; gap:8px; margin-top:12px; }
.tag{
  display:inline-block;
  padding:6px 10px;
  border-radius:999px;
  background:var(--tag);
  color:var(--tagfg);
  border:1px solid var(--tagbd);
  font-size:.86rem;
  font-weight:650;
}

/* Note */
.note{
  margin-top:14px;
  padding:12px 14px;
  border-left:4px solid var(--tagbd);
  background:#f5f7ff;
  border-radius:12px;
  color:#334155;
  line-height:1.6;
}
.note a{ font-weight:800; }

/* ✅ wide note across mid + right (must be direct child of .hero) */
.note-wide{
  grid-column: 2 / 4; /* span mid + right */
  margin-top: 12px;
}

/* Right panel */
.sidepanel{
  background:#fff;
  border:1px solid var(--bd);
  border-radius:16px;
  padding:10px 12px;
}
.srow{
  display:flex;
  gap:10px;
  padding:10px 6px;
}
.srow + .srow{ border-top:1px solid var(--bd); }
.srow .ico{
  width:26px;
  flex:0 0 26px;
  margin-top:2px;
}
.stext{
  min-width:0;
  color:var(--fg);
  line-height:1.55;
}
.sactions{ margin-top:10px; display:flex; flex-wrap:wrap; gap:8px; }
.mini-btn{
  display:inline-block;
  padding:6px 10px;
  border-radius:999px;
  border:1px solid var(--bd);
  background:#fff;
  color:var(--fg);
  font-size:.9rem;
  font-weight:750;
}
.mini-btn:hover{ text-decoration:none; border-color:#cbd5e1; }

/* ===== Publications (v2) ===== */
.pubgroup{
  margin-top: 10px;
}

/* year header */
.pubgroup h3{
  margin: 26px 0 12px;
  font-size: 1.35rem;
  font-weight: 900;
  color: var(--fg);
  letter-spacing: .2px;
  display: flex;
  align-items: center;
  gap: 12px;
}
.pubgroup h3::after{
  content:"";
  height: 1px;
  flex: 1;
  background: var(--bd);
  opacity: .9;
}

/* item card */
.pubitem{
  display: grid;
  grid-template-columns: 160px minmax(0, 1fr);
  gap: 14px;
  padding: 14px;
  border: 1px solid var(--bd);
  border-radius: 16px;
  background: #fff;
  margin: 12px 0;
  transition: transform .08s ease, box-shadow .12s ease, border-color .12s ease;
}
.pubitem:hover{
  transform: translateY(-1px);
  border-color: #cbd5e1;
  box-shadow: 0 10px 24px rgba(15,23,42,.06);
}
.pubimg img{
  width: 160px;
  height: 110px;
  object-fit: cover;
  border: 1px solid var(--bd);
  border-radius: 12px;
  background: #fff;
}

/* text */
.pubtitle{
  font-weight: 900;
  margin: 0 0 6px;
  color: var(--fg);
  line-height: 1.25;
  font-size: 1.05rem;
}
.puba{
  color: var(--muted);
  font-size: .95rem;
  margin: 0 0 6px;
  line-height: 1.45;
}
.pubv{
  color: #334155;
  font-size: .96rem;
  margin: 0;
  line-height: 1.45;
}
.pubv b{ font-weight: 900; }

/* links -> pill buttons */
.publinks{
  margin-top: 10px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.publinks a{
  display: inline-block;
  padding: 6px 10px;
  border-radius: 999px;
  border: 1px solid var(--bd);
  background: #fff;
  color: var(--fg);
  font-size: .92rem;
  font-weight: 750;
  text-decoration: none;
}
.publinks a:hover{
  border-color: #cbd5e1;
}

/* mobile */
@media (max-width: 820px){
  .pubitem{
    grid-template-columns: 1fr;
  }
  .pubimg img{
    width: 100%;
    height: 180px;
  }
}

/* ===== Projects / Research Cards (compact) ===== */
.projwrap{ margin-top: 14px; }
.projlist{ display: grid; gap: 12px; }

.projcard{
  display:flex;
  gap:12px;
  align-items:center;
  padding: 14px 16px;
  background:#fff;
  border:1px solid var(--bd);
  border-radius:16px;
}

.picon{
  width:40px; height:40px;
  flex:0 0 40px;
  border-radius:12px;
  display:grid;
  place-items:center;
  background: var(--tag);
  border:1px solid var(--tagbd);
  font-size:20px;
}

.pbody{ min-width:0; }

.ptitle{
  margin:0;
  color: var(--fg);
  font-weight:900;
  font-size:1.02rem;
  line-height:1.35;
}

.ptitle .en{
  font-weight:700;
  color: var(--muted);
  font-size:.92rem;
  margin-left:6px;
  white-space:nowrap;
}

@media (max-width: 720px){
  .projcard{ padding: 12px 14px; }
  .ptitle .en{ display:block; margin-left:0; margin-top:2px; white-space:normal; }
}

</style>

<!-- ===================== HERO ===================== -->
<div class="hero">

  <!-- Left: photo + ORCID -->
  <div class="leftcol">
    <img class="avatar" src="assets/img/avatar.jpg" alt="Qishi Dong" onerror="this.style.display='none'">
    <div class="small">
      ORCID:
      <a href="https://orcid.org/0009-0005-6994-598X" target="_blank" rel="noopener">0009-0005-6994-598X</a>
    </div>
  </div>

  <!-- Middle: identity -->
  <div class="mid">
    <div class="h1">董其实 <span class="small">| Qishi Dong</span></div>
    <div class="subtitle">深圳技术大学 · 大数据与互联网学院 · 助理教授</div>
    <div class="meta">Statistical learning · Biostatistics · Spatial omics · Deep Learning</div>

    <div class="btns">
      <a class="btn" href="mailto:dongqishi@sztu.edu.cn">Email</a>
      <a class="btn" href="https://scholar.google.com/" target="_blank" rel="noopener">Scholar</a>
      <a class="btn" href="https://github.com/SpatialOmics-pj/dongqishi" target="_blank" rel="noopener">GitHub</a>
    </div>

    <div class="tags">
      <span class="tag">AI for Life Science</span>
      <span class="tag">Bayesian statistics</span>
      <span class="tag">Statistical inference</span>
      <span class="tag">Spatial omics data analysis</span>
    </div>
  </div>

 <!-- Right: clean panel -->
  <div class="right">
    <div class="sidepanel">
      <div class="srow">
        <span class="ico">📍</span>
        <div class="stext">
          中国 · 深圳
          <div class="ssub">Shenzhen, China</div>
        </div>
      </div>

      <div class="srow">
        <span class="ico">🔬</span>
        <div class="stext">
          生命科学中的AI技术 · 贝叶斯统计 · 空间组学数据分析 · 无创生理信号建模与产品落地
        </div>
      </div>

      <div class="srow">
        <span class="ico">🤝</span>
        <div class="stext">
          欢迎与我交流想法与合作
          <div class="sactions">
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ✅ wide note: must be direct child of .hero, placed AFTER mid/right -->
  <div class="note note-wide">
    课题组氛围融洽、结构合理，包含多位博士、硕士和本科生，且有稳定产出。
    欢迎对 <b>数据建模、生物统计、深度学习</b> 与 <b>可穿戴算法落地</b> 感兴趣的同学报考；
    优秀者可直接推荐升学或就业：
    <a href="mailto:dongqishi@sztu.edu.cn">dongqishi@sztu.edu.cn</a>
  </div>

</div>


<!-- ===================== NEWS ===================== -->
<h2 id="news">News</h2>
<ul>
  <li><b>2026</b> · 🎉 祝贺课题组论文 <i>An Empirical Bayes Algorithm for Variable Selection With Applications in Genetic Fine-Mapping</i> 发表于 <b>Stat</b>。</li>
</ul>

<hr/>


<!-- ===================== ABOUT ===================== -->
<h2 id="about">About</h2>
<p class="sectionlead">
我于 2023 年获香港浸会大学统计学博士学位，现为深圳技术大学大数据与互联网学院助理教授。
研究聚焦统计学习、生物统计与医疗健康数据分析，曾在华为诺亚方舟实验室、香港中文大学（深圳）与香港大学从事科研工作。
</p>

<hr/>

<!-- ===================== RESEARCH / PROJECTS ===================== -->
<h2 id="projects">RESEARCH</h2>
<p class="sectionlead">当前在研方向包括：</p>

<div class="projwrap">
  <div class="projlist">

    <div class="projcard">
      <div class="picon">🧭</div>
      <div class="pbody">
        <div class="ptitle">空间单细胞映射算法工具链 <span class="en">(Spatial single-cell mapping)</span></div>
      </div>
    </div>

    <div class="projcard">
      <div class="picon">🤖</div>
      <div class="pbody">
        <div class="ptitle">空间组学智能体与自动化 QC/注释 <span class="en">(Spatial omics agent)</span></div>
      </div>
    </div>

    <div class="projcard">
      <div class="picon">⌚</div>
      <div class="pbody">
        <div class="ptitle">产学合作：森沛科技（深圳）有限公司（PPG/ECG 血压预测算法与产品落地）</div>
      </div>
    </div>

    <div class="projcard">
      <div class="picon">🏥</div>
      <div class="pbody">
        <div class="ptitle">医院合作：解放军总医院（301 医院）空间多组学数据分析</div>
      </div>
    </div>

    <div class="projcard">
      <div class="picon">🤝</div>
      <div class="pbody">
        <div class="ptitle">高校合作：四川大学空间解卷积算法开发</div>
      </div>
    </div>

  </div>
</div>

<hr/>


<!-- ===================== PUBLICATIONS ===================== -->
<h2 id="publications">Publications</h2>

<div class="pubgroup">

  <h3>2026</h3>

  <div class="pubitem">
    <div class="pubimg">
      <img src="assets/img/pubs/fusion.png" alt="FUSION" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="pubtitle">Composition-Aware Cross-Sectional Integration for Spatial Transcriptomics</div>
      <div class="puba">Dong, Q.†; Huang, Z.†; Wang, X.; Feng, Z.; Liu, W.; Huang, B.*</div>
      <div class="pubv"><b>Advanced Intelligent Discovery</b>, 2026</div>
      <div class="publinks">
        <a href="/assets/papers/FUSION.pdf">PDF</a>
      </div>
    </div>
  </div>

  <div class="pubitem">
    <div class="pubimg">
      <img src="assets/img/pubs/empbvs.png" alt="EmpBVS" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="pubtitle">An Empirical Bayes Algorithm for Variable Selection With Applications in Genetic Fine-Mapping</div>
      <div class="puba">Dong, Q.*; Wang, X.*; Guan, X.; Liang, L.; Ke, X.#; Peng, H.</div>
      <div class="pubv"><b>Stat</b>, 2026</div>
      <div class="publinks">
        <a href="/assets/papers/EmpBVS_clean.pdf">PDF</a>
      </div>
    </div>
  </div>

  <h3>2025</h3>

  <div class="pubitem">
    <div class="pubimg">
      <img src="assets/img/pubs/qrside.png" alt="QR-SIDE" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="pubtitle">Robust Spatial Cell-Type Deconvolution with Qualitative Reference for Spatial Transcriptomics</div>
      <div class="puba">Dong, Q.*; Yang, Y.*; Luo, Z.; Shen, H.; Shi, X.#; Liu, J.#</div>
      <div class="pubv"><b>Small Methods</b> 9(5), 2401145, 2025</div>
      <div class="publinks">
        <a href="#">Paper</a>
      </div>
    </div>
  </div>

  <h3>2023</h3>

  <div class="pubitem">
    <div class="pubimg">
      <img src="assets/img/pubs/damix.png" alt="DAMix" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="pubtitle">DAMix: Exploiting Deep Autoregressive Model Zoo for Improving Lossless Compression Generalization</div>
      <div class="puba">Dong, Q.; Zhou, F.; Kang, N.; Xie, C.; Zhang, S.; Li, J.; Peng, H.; Li, Z.*</div>
      <div class="pubv"><b>AAAI</b>, 2023</div>
      <div class="publinks">
        <a href="#">Paper</a>
      </div>
    </div>
  </div>

  <h3>2022</h3>

  <div class="pubitem">
    <div class="pubimg">
      <img src="assets/img/pubs/zood.png" alt="ZooD" onerror="this.style.display='none'">
    </div>
    <div>
      <div class="pubtitle">ZooD: Exploiting Model Zoo for Out-of-Distribution Generalization</div>
      <div class="puba">Dong, Q.; Muhammad, A.; Zhou, F.; Xie, C.; Hu, T.; Yang, Y.; Bae, S.-H.; Li, Z.*</div>
      <div class="pubv"><b>NeurIPS</b>, 2022</div>
      <div class="publinks">
        <a href="#">Paper</a>
      </div>
    </div>
  </div>

</div>

<hr/>

<!-- ===================== PATENTS ===================== -->
<h2 id="patents">Patents</h2>
<ul>
  <li>
    <b>发明专利申请（已受理）</b>：申请号 <b>202511359756.X</b>，
    “一种联合解卷积域识别与对齐的方法、系统、终端及介质”（发文日：2025-09-23）。
  </li>
</ul>

<hr/>

<!-- ===================== INDUSTRY ===================== -->
<h2 id="industry">Industry Collaboration</h2>
<ul>
  <li><b>森沛科技（深圳）有限公司 × 深圳技术大学</b>：智能穿戴端 PPG 信号的可校准预测算法优化（2026.02–2026.12）。</li>
</ul>

<hr/>

<!-- ===================== CONTACT ===================== -->
<h2 id="contact">Contact</h2>
<ul>
  <li>Email: <a href="mailto:dongqishi@sztu.edu.cn">dongqishi@sztu.edu.cn</a></li>
  <li>ORCID: <a href="https://orcid.org/0009-0005-6994-598X" target="_blank" rel="noopener">0009-0005-6994-598X</a></li>
  <li>GitHub: <a href="https://github.com/SpatialOmics-pj/dongqishi" target="_blank" rel="noopener">SpatialOmics-pj/dongqishi</a></li>
</ul>
