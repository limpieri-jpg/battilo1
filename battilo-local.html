import React, { useState, useEffect } from "react";

const ROYALTY_MOBILE = 8;    // Commissione beni MOBILI (%) — a carico acquirente

// Commissione IMMOBILI per fascia di prezzo (aggiornabile dall'admin)
const FASCE_IMMOBILE = [
  { max: 100000,   pct: 4.0, label: "fino a € 100.000" },
  { max: 250000,   pct: 3.5, label: "€ 100.001 – 250.000" },
  { max: 500000,   pct: 3.0, label: "€ 250.001 – 500.000" },
  { max: 1000000,  pct: 2.5, label: "€ 500.001 – 1.000.000" },
  { max: Infinity, pct: 2.0, label: "oltre € 1.000.000" },
];

// Helper: restituisce % per immobili in base al prezzo
const getRoyaltyImmobile = (price) => {
  const p = parseFloat(price) || 0;
  const fascia = FASCE_IMMOBILE.find(f => p <= f.max);
  return fascia ? fascia.pct : 2.0;
};

// Helper generale
const getRoyalty = (cat, price) =>
  cat === "Immobili" ? getRoyaltyImmobile(price) : ROYALTY_MOBILE;

// ── CAUZIONE ──────────────────────────────────────────────────────────────────
// Modalità: "pct" = percentuale sul prezzo base | "fixed" = importo fisso
// ── SERVIZIO FOTOGRAFICO & VIRTUAL TOUR (configurabile da admin) ──────────────
const FOTO_SERVICE_ENABLED = true;       // abilita/disabilita il servizio
const FOTO_IMMOBILE_PRICE  = 350;        // € servizio foto + video immobili
const VIRTUAL_TOUR_PRICE   = 490;        // € virtual tour 3D Matterport
const FOTO_BUNDLE_PRICE    = 750;        // € bundle foto immobile + virtual tour

const CAUZIONE_MODE = "pct";   // "pct" | "fixed"
const CAUZIONE_PCT  = 10;      // % sul prezzo base (standard aste italiane)
const CAUZIONE_FIXED = 500;    // € importo fisso alternativo
// Helper: calcola cauzione
const calcCauzione = (price) => {
  const p = parseFloat(price) || 0;
  if (!p) return 0;
  return CAUZIONE_MODE === "pct"
    ? Math.round(p * CAUZIONE_PCT / 100)
    : CAUZIONE_FIXED;
};
const cauzioneLabel = () =>
  CAUZIONE_MODE === "pct" ? `${CAUZIONE_PCT}% del prezzo base` : `€ ${CAUZIONE_FIXED.toLocaleString("it")} fissi`;

const CSS = `
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap');
*{box-sizing:border-box;margin:0;padding:0;}
:root{
  --cream:#F7F3EE;--warm:#FDFAF6;--amber:#C8852A;--amber-l:#E8A84C;--amber-p:#F5E6CE;
  --char:#1C1A17;--muted:#6B6560;--border:#E2D9CE;--red:#C0392B;--green:#2D6A4F;
  --blue:#1A4D7C;--blue-l:#e8f0fa;
}
body{font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--char);min-height:100vh;}
/* NAV */
.nav{position:sticky;top:0;z-index:100;background:rgba(247,243,238,0.95);backdrop-filter:blur(14px);border-bottom:1px solid var(--border);padding:0 2rem;display:flex;align-items:center;justify-content:space-between;height:68px;gap:1.5rem;}
.nav-links{display:flex;gap:1.75rem;}
.nav-links a{font-size:.78rem;letter-spacing:.07em;text-transform:uppercase;color:var(--muted);text-decoration:none;cursor:pointer;transition:color .2s;}
.nav-links a:hover{color:var(--amber);}
.nav-actions{display:flex;gap:.7rem;align-items:center;}
.btn-ghost{background:none;border:1px solid var(--border);padding:.42rem 1rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.75rem;letter-spacing:.05em;text-transform:uppercase;color:var(--char);cursor:pointer;transition:all .2s;}
.btn-ghost:hover{border-color:var(--amber);color:var(--amber);}
.btn-primary{background:var(--amber);border:none;padding:.46rem 1.2rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.75rem;letter-spacing:.05em;text-transform:uppercase;color:#fff;cursor:pointer;transition:all .2s;}
.btn-primary:hover{background:var(--amber-l);}
.user-chip{display:flex;align-items:center;gap:.45rem;background:var(--amber-p);border:1px solid var(--border);padding:.3rem .8rem .3rem .48rem;border-radius:20px;cursor:pointer;font-size:.76rem;color:var(--char);transition:all .2s;}
.user-chip:hover{border-color:var(--amber);}
.avatar{width:26px;height:26px;border-radius:50%;background:var(--amber);color:#fff;font-size:.7rem;display:flex;align-items:center;justify-content:center;font-weight:500;}
/* HERO */
.hero{background:var(--char);padding:5rem 2rem 4rem;position:relative;overflow:hidden;}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 68% 50%,rgba(200,133,42,.22) 0%,transparent 60%);}
.hero-inner{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;position:relative;}
.hero-tag{display:inline-block;font-size:.66rem;letter-spacing:.13em;text-transform:uppercase;color:var(--amber);border:1px solid var(--amber);padding:.22rem .7rem;margin-bottom:1.4rem;border-radius:1px;}
.hero h1{font-family:'Cormorant Garamond',serif;font-size:clamp(2.2rem,5vw,3.7rem);font-weight:300;line-height:1.15;color:var(--warm);margin-bottom:1.2rem;}
.hero h1 em{font-style:italic;color:var(--amber-l);}
.hero p{color:rgba(253,250,246,.55);font-size:.9rem;line-height:1.8;margin-bottom:2rem;}
.hero-acts{display:flex;gap:1rem;flex-wrap:wrap;}
.bhf{padding:.72rem 1.8rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.78rem;letter-spacing:.07em;text-transform:uppercase;cursor:pointer;background:var(--amber);color:#fff;border:1px solid var(--amber);transition:all .25s;}
.bhf:hover{background:var(--amber-l);}
.bho{padding:.72rem 1.8rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.78rem;letter-spacing:.07em;text-transform:uppercase;cursor:pointer;background:transparent;color:var(--warm);border:1px solid rgba(253,250,246,.28);transition:all .25s;}
.bho:hover{border-color:var(--amber);color:var(--amber);}
.hbox{background:rgba(253,250,246,.05);border:1px solid rgba(253,250,246,.1);border-radius:4px;padding:2rem;}
.hbox h3{font-family:'Cormorant Garamond',serif;font-size:1rem;color:rgba(253,250,246,.4);font-weight:300;letter-spacing:.05em;margin-bottom:1.5rem;}
.sg{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
.sn{font-family:'Cormorant Garamond',serif;font-size:2rem;font-weight:600;color:var(--amber-l);line-height:1;}
.sl{font-size:.68rem;letter-spacing:.08em;text-transform:uppercase;color:rgba(253,250,246,.34);margin-top:.18rem;}
.sdiv{border:none;border-top:1px solid rgba(253,250,246,.07);margin:1.5rem 0;}
.cdw{display:flex;gap:.5rem;align-items:flex-end;}
.cdu{text-align:center;}
.cdn{font-family:'Cormorant Garamond',serif;font-size:1.75rem;font-weight:600;color:var(--warm);line-height:1;background:rgba(253,250,246,.05);padding:.28rem .55rem;border-radius:2px;min-width:2.6rem;display:block;text-align:center;}
.cds{font-family:'Cormorant Garamond',serif;font-size:1.3rem;color:var(--amber);margin-bottom:.22rem;}
.cdl{font-size:.56rem;letter-spacing:.08em;text-transform:uppercase;color:rgba(253,250,246,.28);margin-top:.2rem;display:block;text-align:center;}
.cdtitle{font-size:.66rem;letter-spacing:.1em;text-transform:uppercase;color:rgba(253,250,246,.34);margin-bottom:.7rem;}
/* SEARCH BAR */
.sbar{background:var(--warm);border-bottom:1px solid var(--border);padding:1.1rem 2rem;}
.sbar-in{max-width:1100px;margin:0 auto;display:flex;gap:1rem;align-items:center;flex-wrap:wrap;}
.sbox{flex:1;min-width:200px;display:flex;align-items:center;gap:.65rem;background:var(--cream);border:1px solid var(--border);padding:.54rem .92rem;border-radius:2px;transition:border-color .2s;}
.sbox:focus-within{border-color:var(--amber);}
.sbox input{flex:1;border:none;background:none;font-family:'DM Sans',sans-serif;font-size:.84rem;color:var(--char);outline:none;}
.pills{display:flex;gap:.4rem;flex-wrap:wrap;}
.pill{padding:.28rem .82rem;border-radius:20px;font-size:.72rem;letter-spacing:.03em;border:1px solid var(--border);background:transparent;color:var(--muted);cursor:pointer;transition:all .2s;}
.pill:hover,.pill.on{background:var(--amber);border-color:var(--amber);color:#fff;}
/* CARDS */
.main{max-width:1100px;margin:0 auto;padding:3rem 2rem;}
.sh{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:2rem;}
.st{font-family:'Cormorant Garamond',serif;font-size:1.75rem;font-weight:400;}
.st span{color:var(--amber);font-style:italic;}
.sl2{font-size:.74rem;letter-spacing:.07em;text-transform:uppercase;color:var(--amber);cursor:pointer;border-bottom:1px solid transparent;transition:border-color .2s;}
.sl2:hover{border-color:var(--amber);}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(278px,1fr));gap:1.5rem;}
.card{background:var(--warm);border:1px solid var(--border);border-radius:3px;overflow:hidden;cursor:pointer;transition:all .25s;position:relative;}
.card:hover{transform:translateY(-3px);box-shadow:0 14px 42px rgba(28,26,23,.1);border-color:var(--amber-p);}
.ci{height:198px;overflow:hidden;position:relative;background:var(--amber-p);}
.ci img{width:100%;height:100%;object-fit:cover;transition:transform .4s;}
.card:hover .ci img{transform:scale(1.04);}
.cbadge{position:absolute;top:.7rem;left:.7rem;background:var(--char);color:var(--amber-l);font-size:.6rem;letter-spacing:.1em;text-transform:uppercase;padding:.17rem .52rem;border-radius:1px;}
.cbadge-buy{position:absolute;top:.7rem;left:50%;transform:translateX(-50%);background:var(--green);color:#fff;font-size:.6rem;letter-spacing:.1em;text-transform:uppercase;padding:.17rem .65rem;border-radius:1px;white-space:nowrap;}
.cfav{position:absolute;top:.7rem;right:.7rem;background:rgba(253,250,246,.9);border:none;width:30px;height:30px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.92rem;transition:all .2s;}
.cfav:hover{background:#fff;}
.cb{padding:1rem 1.2rem 1.2rem;}
.ccat{font-size:.63rem;letter-spacing:.1em;text-transform:uppercase;color:var(--amber);margin-bottom:.32rem;}
.ctitle{font-family:'Cormorant Garamond',serif;font-size:1.16rem;font-weight:500;line-height:1.3;margin-bottom:.65rem;}
.cmeta{display:flex;justify-content:space-between;align-items:center;margin-bottom:.65rem;}
.plbl{font-size:.6rem;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);}
.pval{font-family:'Cormorant Garamond',serif;font-size:1.42rem;font-weight:600;}
.cbids{font-size:.73rem;color:var(--muted);text-align:right;}
.cbids strong{color:var(--char);}
.cfoot{border-top:1px solid var(--border);padding-top:.68rem;display:flex;justify-content:space-between;align-items:center;}
.ctimer{display:flex;align-items:center;gap:.36rem;font-size:.74rem;}
.tdot{width:6px;height:6px;border-radius:50%;animation:pulse 1.5s infinite;}
.tg{background:var(--green);}.ty{background:#E6A817;}.tr{background:var(--red);}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.6;transform:scale(.85);}}
.resb{font-size:.62rem;letter-spacing:.04em;padding:.13rem .46rem;border-radius:1px;}
.rok{background:rgba(45,106,79,.12);color:var(--green);}
.rno{background:rgba(192,57,43,.1);color:var(--red);}
/* OVERLAY / MODALS */
.ov{position:fixed;inset:0;z-index:200;background:rgba(28,26,23,.72);display:flex;align-items:center;justify-content:center;padding:1rem;animation:fi .2s ease;}
@keyframes fi{from{opacity:0;}to{opacity:1;}}
.modal{background:var(--warm);border-radius:4px;max-width:900px;width:100%;max-height:90vh;overflow-y:auto;animation:su .25s ease;}
.smodal{background:var(--warm);border-radius:4px;max-width:680px;width:100%;max-height:93vh;overflow-y:auto;animation:su .25s ease;}
.lmodal{background:var(--warm);border-radius:4px;max-width:560px;width:100%;max-height:93vh;overflow-y:auto;animation:su .25s ease;}
@keyframes su{from{transform:translateY(18px);opacity:0;}to{transform:translateY(0);opacity:1;}}
.mhdr{display:flex;justify-content:space-between;align-items:center;padding:1.2rem 1.5rem;border-bottom:1px solid var(--border);position:sticky;top:0;background:var(--warm);z-index:10;}
.mhdr h2{font-family:'Cormorant Garamond',serif;font-size:1.28rem;font-weight:500;}
.mcl{background:none;border:1px solid var(--border);width:32px;height:32px;border-radius:2px;cursor:pointer;font-size:1rem;color:var(--muted);display:flex;align-items:center;justify-content:center;transition:all .2s;}
.mcl:hover{border-color:var(--char);color:var(--char);}
/* DETAIL MODAL */
.mbody{display:grid;grid-template-columns:1fr 1fr;gap:2rem;padding:1.5rem;}
.gmain{width:100%;height:272px;object-fit:cover;border-radius:2px;margin-bottom:.68rem;background:var(--amber-p);}
.gthumbs{display:flex;gap:.42rem;}
.gth{width:56px;height:56px;object-fit:cover;border-radius:1px;cursor:pointer;border:2px solid transparent;transition:border-color .15s;background:var(--amber-p);}
.gth.on{border-color:var(--amber);}
.mcat{font-size:.64rem;letter-spacing:.12em;text-transform:uppercase;color:var(--amber);margin-bottom:.42rem;}
.mtitle{font-family:'Cormorant Garamond',serif;font-size:1.68rem;font-weight:400;line-height:1.2;margin-bottom:.42rem;}
.mcond{display:inline-block;font-size:.66rem;letter-spacing:.07em;background:var(--amber-p);color:var(--amber);padding:.17rem .52rem;border-radius:1px;margin-bottom:1rem;}
.mdesc{font-size:.84rem;line-height:1.8;color:var(--muted);margin-bottom:1.35rem;}
.bidbox{background:var(--cream);border:1px solid var(--border);border-radius:3px;padding:1.15rem;margin-bottom:.85rem;}
.br{display:flex;justify-content:space-between;margin-bottom:.4rem;}
.bk{font-size:.73rem;color:var(--muted);}
.bv{font-family:'Cormorant Garamond',serif;font-size:1.02rem;font-weight:600;}
.resind{display:flex;align-items:center;gap:.46rem;font-size:.75rem;margin-bottom:.85rem;}
.rsdot{width:8px;height:8px;border-radius:50%;}
.bform{display:flex;gap:.43rem;margin-top:.85rem;}
.bin{flex:1;border:1px solid var(--border);background:var(--warm);padding:.56rem .88rem;border-radius:2px;font-family:'Cormorant Garamond',serif;font-size:1.02rem;color:var(--char);outline:none;transition:border-color .2s;}
.bin:focus{border-color:var(--amber);}
.bsub{background:var(--amber);color:#fff;border:none;padding:.56rem 1.28rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.76rem;letter-spacing:.06em;text-transform:uppercase;cursor:pointer;transition:background .2s;white-space:nowrap;}
.bsub:hover{background:var(--amber-l);}
.bhtitle{font-size:.66rem;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);margin-bottom:.68rem;display:flex;align-items:center;gap:.43rem;}
.ldot{width:6px;height:6px;border-radius:50%;background:var(--green);animation:pulse 1.5s infinite;}
.bhitem{display:flex;justify-content:space-between;align-items:center;padding:.46rem 0;border-bottom:1px solid var(--border);font-size:.78rem;}
.bhitem:last-child{border-bottom:none;}
.bhu{color:var(--char);font-weight:500;}
.bha{font-family:'Cormorant Garamond',serif;font-size:.96rem;font-weight:600;}
.bht{color:var(--muted);font-size:.7rem;}
/* SELL STEPS */
.ssteps{display:flex;border-bottom:1px solid var(--border);background:var(--cream);}
.ss{flex:1;padding:.68rem .5rem;text-align:center;font-size:.62rem;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);border-bottom:2px solid transparent;transition:all .2s;}
.ss.done{color:var(--green);}
.ss.act{color:var(--amber);border-bottom-color:var(--amber);}
.sbody{padding:1.5rem 1.8rem;}
.stitle{font-family:'Cormorant Garamond',serif;font-size:1.4rem;font-weight:400;margin-bottom:.35rem;}
.ssub{font-size:.8rem;color:var(--muted);margin-bottom:1.55rem;line-height:1.6;}
.fg{display:flex;flex-direction:column;gap:.36rem;margin-bottom:.95rem;}
.fl{font-size:.66rem;letter-spacing:.08em;text-transform:uppercase;color:var(--muted);}
.fi{border:1px solid var(--border);background:var(--cream);border-radius:2px;padding:.58rem .88rem;font-family:'DM Sans',sans-serif;font-size:.86rem;color:var(--char);outline:none;transition:border-color .2s;width:100%;}
.fi:focus{border-color:var(--amber);}
.fi::placeholder{color:#bbb;}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.upzone{border:2px dashed var(--border);border-radius:3px;padding:2rem;text-align:center;cursor:pointer;transition:all .25s;background:var(--cream);}
.upzone:hover{border-color:var(--amber);background:var(--amber-p);}
.upzone.uploading{border-color:var(--amber);background:rgba(200,133,42,.04);}
.upicon{font-size:1.9rem;margin-bottom:.5rem;opacity:.4;}
.uptxt{font-size:.78rem;color:var(--muted);line-height:1.7;}
.uptxt strong{color:var(--amber);}
.upprev{display:flex;gap:.5rem;flex-wrap:wrap;margin-top:.9rem;}
.upprevit{position:relative;width:66px;height:66px;}
.upprevit img{width:100%;height:100%;object-fit:cover;border-radius:2px;border:1px solid var(--border);}
.updel{position:absolute;top:-6px;right:-6px;width:17px;height:17px;border-radius:50%;background:var(--red);color:#fff;border:none;font-size:.58rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}
.resnote{background:rgba(200,133,42,.08);border:1px solid rgba(200,133,42,.25);border-radius:2px;padding:.78rem .92rem;margin-bottom:.95rem;font-size:.78rem;color:var(--char);line-height:1.65;}
.resnote strong{color:var(--amber);}
.roybox{background:rgba(45,106,79,.06);border:1px solid rgba(45,106,79,.2);border-radius:2px;padding:.88rem 1.1rem;margin-bottom:1rem;font-size:.8rem;color:var(--char);line-height:1.7;}
.roybox strong{color:var(--green);}
.lottoggle{display:flex;align-items:flex-start;gap:.68rem;cursor:pointer;padding:.68rem .92rem;border:1px solid var(--border);border-radius:2px;background:var(--cream);transition:all .2s;margin-bottom:.68rem;}
.lottoggle:hover{border-color:var(--amber);}
.lottoggle input{accent-color:var(--amber);width:14px;height:14px;margin-top:.12rem;flex-shrink:0;}
.lotlbl{font-size:.83rem;color:var(--char);}
.lotsub{font-size:.71rem;color:var(--muted);}
.sacts{display:flex;justify-content:space-between;align-items:center;padding:1.15rem 1.8rem;border-top:1px solid var(--border);position:sticky;bottom:0;background:var(--warm);}
.sprog{font-size:.71rem;color:var(--muted);}
.sprog strong{color:var(--amber);}
.snext{background:var(--amber);border:none;padding:.6rem 1.65rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.78rem;letter-spacing:.06em;text-transform:uppercase;color:#fff;cursor:pointer;transition:all .2s;}
.snext:hover{background:var(--amber-l);}
.sback{background:none;border:1px solid var(--border);padding:.6rem 1.25rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.78rem;letter-spacing:.06em;text-transform:uppercase;color:var(--char);cursor:pointer;transition:all .2s;}
.sback:hover{border-color:var(--amber);color:var(--amber);}
.chrow{display:flex;align-items:flex-start;gap:.58rem;margin-bottom:.68rem;cursor:pointer;}
.chrow input{accent-color:var(--amber);width:14px;height:14px;margin-top:.14rem;flex-shrink:0;}
.chrow span{font-size:.78rem;color:var(--char);line-height:1.55;}
.succ{text-align:center;padding:2.6rem 2rem;}
.succicon{font-size:3rem;margin-bottom:.9rem;}
.succtitle{font-family:'Cormorant Garamond',serif;font-size:1.85rem;margin-bottom:.65rem;color:var(--green);}
.succmsg{font-size:.83rem;color:var(--muted);line-height:1.8;margin-bottom:1.7rem;}
/* ---- REGISTRATION MODAL ---- */
.regbody{padding:1.6rem 1.8rem;}
.reg-section{margin-bottom:1.6rem;}
.reg-section-title{font-family:'Cormorant Garamond',serif;font-size:1.1rem;font-weight:600;color:var(--char);margin-bottom:.8rem;padding-bottom:.5rem;border-bottom:1px solid var(--border);}
.legal-box{background:#FFF8F0;border:1px solid rgba(200,133,42,.35);border-radius:3px;padding:1.1rem 1.25rem;margin-bottom:1rem;font-size:.8rem;line-height:1.8;color:var(--char);}
.legal-box h4{font-size:.78rem;letter-spacing:.07em;text-transform:uppercase;color:var(--amber);margin-bottom:.65rem;}
.legal-box ul{padding-left:1.1rem;}
.legal-box ul li{margin-bottom:.35rem;}
.legal-box strong{color:var(--amber);}
.id-upload{border:2px dashed var(--border);border-radius:3px;padding:1.5rem;text-align:center;cursor:pointer;transition:all .25s;background:var(--cream);margin-top:.6rem;}
.id-upload:hover{border-color:var(--amber);background:var(--amber-p);}
.id-upload.done{border-color:var(--green);background:rgba(45,106,79,.04);}
.id-icon{font-size:1.7rem;margin-bottom:.4rem;}
.id-txt{font-size:.77rem;color:var(--muted);line-height:1.6;}
.id-txt strong{color:var(--amber);}
.id-txt.ok{color:var(--green);}
.royalty-info{background:rgba(45,106,79,.07);border:1px solid rgba(45,106,79,.22);border-radius:3px;padding:1rem 1.2rem;font-size:.8rem;line-height:1.7;margin-bottom:1rem;}
.royalty-info h4{font-size:.76rem;letter-spacing:.07em;text-transform:uppercase;color:var(--green);margin-bottom:.6rem;}
.royalty-info strong{color:var(--green);}
.royalty-pct{font-family:'Cormorant Garamond',serif;font-size:2.2rem;font-weight:600;color:var(--green);display:block;text-align:center;margin:.5rem 0;}
.warn-box{background:rgba(192,57,43,.06);border:1px solid rgba(192,57,43,.2);border-radius:3px;padding:.9rem 1.1rem;margin-bottom:.9rem;font-size:.78rem;color:var(--char);line-height:1.7;}
.warn-box strong{color:var(--red);}
/* ADMIN */
.adm{background:var(--char);min-height:100vh;color:var(--warm);}
.admnav{background:rgba(253,250,246,.04);border-bottom:1px solid rgba(253,250,246,.08);padding:0 2rem;height:60px;display:flex;align-items:center;gap:1rem;}
.admcont{padding:2rem;max-width:1100px;margin:0 auto;}
.admstats{display:grid;grid-template-columns:repeat(4,1fr);gap:1rem;margin-bottom:2.5rem;}
.asc{background:rgba(253,250,246,.04);border:1px solid rgba(253,250,246,.08);border-radius:3px;padding:1.15rem;}
.ascl{font-size:.64rem;letter-spacing:.1em;text-transform:uppercase;color:rgba(253,250,246,.28);margin-bottom:.42rem;}
.ascn{font-family:'Cormorant Garamond',serif;font-size:1.85rem;font-weight:600;color:var(--amber-l);}
.admtitle{font-family:'Cormorant Garamond',serif;font-size:1.32rem;font-weight:300;color:var(--warm);margin-bottom:1.15rem;}
.tabs{display:flex;border-bottom:1px solid rgba(253,250,246,.08);margin-bottom:2rem;}
.tab{padding:.7rem 1.38rem;font-size:.74rem;letter-spacing:.07em;text-transform:uppercase;color:rgba(253,250,246,.3);cursor:pointer;border-bottom:2px solid transparent;margin-bottom:-1px;transition:all .2s;}
.tab:hover{color:rgba(253,250,246,.6);}
.tab.on{color:var(--amber-l);border-bottom-color:var(--amber);}
.afg{display:flex;flex-direction:column;gap:.34rem;margin-bottom:.88rem;}
.afl{font-size:.66rem;letter-spacing:.08em;text-transform:uppercase;color:rgba(253,250,246,.36);}
.afi{background:rgba(253,250,246,.05);border:1px solid rgba(253,250,246,.1);border-radius:2px;padding:.56rem .86rem;font-family:'DM Sans',sans-serif;font-size:.85rem;color:var(--warm);outline:none;transition:border-color .2s;width:100%;}
.afi:focus{border-color:var(--amber);}
.afi::placeholder{color:rgba(253,250,246,.17);}
.afrow{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.admup{border:2px dashed rgba(253,250,246,.12);border-radius:3px;padding:1.8rem;text-align:center;cursor:pointer;transition:border-color .2s;margin-bottom:.9rem;}
.admup:hover{border-color:var(--amber);}
.admacts{display:flex;gap:1rem;justify-content:flex-end;}
.bag{padding:.56rem 1.45rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.76rem;letter-spacing:.06em;text-transform:uppercase;cursor:pointer;transition:all .2s;background:none;border:1px solid rgba(253,250,246,.13);color:rgba(253,250,246,.5);}
.bag:hover{border-color:rgba(253,250,246,.36);color:var(--warm);}
.baf{padding:.56rem 1.45rem;border-radius:2px;font-family:'DM Sans',sans-serif;font-size:.76rem;letter-spacing:.06em;text-transform:uppercase;cursor:pointer;transition:all .2s;background:var(--amber);border:1px solid var(--amber);color:#fff;}
.baf:hover{background:var(--amber-l);}
.modit{display:flex;justify-content:space-between;align-items:center;padding:.9rem;background:rgba(253,250,246,.03);border:1px solid rgba(253,250,246,.07);border-radius:2px;margin-bottom:.65rem;}
.modname{font-size:.86rem;}
.modseller{font-size:.71rem;color:rgba(253,250,246,.34);}
.seller-badge{display:inline-flex;align-items:center;gap:.35rem;font-size:.66rem;letter-spacing:.06em;padding:.15rem .5rem;border-radius:10px;}
.sb-ok{background:rgba(45,106,79,.18);color:#3aaa78;}
.sb-pending{background:rgba(200,133,42,.18);color:var(--amber-l);}
.sb-rejected{background:rgba(192,57,43,.18);color:#e05c4e;}
/* ROYALTY PANEL */
.roy-row{display:flex;justify-content:space-between;align-items:center;padding:.85rem .95rem;background:rgba(253,250,246,.03);border:1px solid rgba(253,250,246,.07);border-radius:2px;margin-bottom:.6rem;}
.roy-info{font-size:.82rem;}
.roy-amount{font-family:'Cormorant Garamond',serif;font-size:1.1rem;font-weight:600;color:var(--amber-l);}
.roy-status{font-size:.66rem;letter-spacing:.06em;text-transform:uppercase;padding:.13rem .44rem;border-radius:1px;}
.rs-paid{background:rgba(45,106,79,.2);color:#3aaa78;}
.rs-pending{background:rgba(200,133,42,.18);color:var(--amber-l);}
/* ROYALTY INPUT ADMIN */
.pct-row{display:flex;align-items:center;gap:1rem;margin-bottom:1.5rem;}
.pct-input{width:100px;background:rgba(253,250,246,.05);border:1px solid rgba(253,250,246,.15);border-radius:2px;padding:.55rem .8rem;font-family:'Cormorant Garamond',serif;font-size:1.4rem;color:var(--amber-l);outline:none;text-align:center;}
.pct-input:focus{border-color:var(--amber);}
/* FOOTER */
.footer{background:var(--char);border-top:1px solid rgba(253,250,246,.06);padding:3rem 2rem;margin-top:4rem;}
.fin{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:3rem;}
.ftag{font-size:.78rem;color:rgba(253,250,246,.3);line-height:1.7;margin-top:.65rem;}
.fcol h4{font-size:.64rem;letter-spacing:.12em;text-transform:uppercase;color:rgba(253,250,246,.28);margin-bottom:.9rem;}
.fcol a{display:block;font-size:.78rem;color:rgba(253,250,246,.44);text-decoration:none;margin-bottom:.46rem;cursor:pointer;transition:color .2s;}
.fcol a:hover{color:var(--amber-l);}
.fbot{max-width:1100px;margin:2rem auto 0;padding-top:1.35rem;border-top:1px solid rgba(253,250,246,.06);display:flex;justify-content:space-between;font-size:.69rem;color:rgba(253,250,246,.17);}
.psw{position:fixed;bottom:1.5rem;right:1.5rem;z-index:300;display:flex;gap:.42rem;}
.pb{padding:.4rem .88rem;border-radius:20px;font-size:.68rem;letter-spacing:.06em;text-transform:uppercase;cursor:pointer;transition:all .2s;border:1px solid;}
.pbl{background:var(--warm);border-color:var(--border);color:var(--char);}
.pbd{background:var(--char);border-color:rgba(253,250,246,.2);color:var(--warm);}
.pb.sel{background:var(--amber);border-color:var(--amber);color:#fff;}
.empty{text-align:center;padding:4rem 2rem;color:var(--muted);}
.welc{background:linear-gradient(135deg,var(--amber-p),var(--cream));border:1px solid var(--border);border-radius:3px;padding:1.15rem 1.4rem;margin-bottom:2rem;display:flex;justify-content:space-between;align-items:center;gap:1rem;flex-wrap:wrap;}
@media(max-width:768px){.hero-inner,.mbody{grid-template-columns:1fr;}.fin{grid-template-columns:1fr 1fr;}.admstats,.sg{grid-template-columns:1fr 1fr;}.frow,.afrow{grid-template-columns:1fr;}.nav-links{display:none;}}
`;

/* ─── LOGO BATTILO ─── */
function Logo({ size = 44, textSize = "1.42rem", dark = false }) {
  const c = dark ? "#FDFAF6" : "#1C1A17";
  const a = "#C8852A";
  return (
    <div style={{ display:"flex", alignItems:"center", gap:".5rem" }}>
      <svg width={size} height={size} viewBox="0 0 52 52" fill="none" xmlns="http://www.w3.org/2000/svg">
        {/* Base circle */}
        <circle cx="26" cy="26" r="24" stroke={a} strokeWidth="1.3" fill="none" opacity="0.35"/>
        <circle cx="26" cy="26" r="19" stroke={a} strokeWidth=".6" fill="none" opacity="0.18"/>
        {/* Gavel head — rotated rectangle */}
        <rect x="8" y="20" width="20" height="9" rx="2.5" fill={a}
          transform="rotate(-38 18 24.5)" opacity="0.92"/>
        {/* Gavel handle */}
        <line x1="26" y1="30" x2="41" y2="44" stroke={a} strokeWidth="3.2"
          strokeLinecap="round" opacity="0.82"/>
        {/* Strike sparks */}
        <line x1="32" y1="10" x2="36" y2="6" stroke={a} strokeWidth="1.8" strokeLinecap="round" opacity="0.65"/>
        <line x1="37" y1="15" x2="42" y2="12" stroke={a} strokeWidth="1.5" strokeLinecap="round" opacity="0.5"/>
        <line x1="32" y1="19" x2="37" y2="17" stroke={a} strokeWidth="1.2" strokeLinecap="round" opacity="0.38"/>
        {/* Dot */}
        <circle cx="26" cy="26" r="2.8" fill={a} opacity="0.18"/>
      </svg>
      <div style={{ display:"flex", flexDirection:"column", lineHeight:1 }}>
        <span style={{
          fontFamily:"'Cormorant Garamond',serif",
          fontSize: textSize, fontWeight:600,
          color: c, letterSpacing:".02em"
        }}>
          <span style={{color:a}}>B</span>attilo
        </span>
        <span style={{
          fontFamily:"'DM Sans',sans-serif",
          fontSize:".48rem", letterSpacing:".18em",
          textTransform:"uppercase", color:a, opacity:.7, marginTop:"2px"
        }}>aste · privati · italia</span>
      </div>
    </div>
  );
}

/* ─── DATA ─── */
const ITEMS = [
  { id:1, buyNow:true, buyNowPrice:420, cat:"Arte", ivaEsposta:false, regimeFiscale:"privato", title:"Olio su tela — Paesaggio Toscano", cond:"Ottimo", price:340, bids:7, left:"2h 14m", ts:"yellow", res:true, lot:false, desc:"Dipinto a olio su tela di fine Ottocento, colline toscane al tramonto. Cornice coeva in legno dorato. Firma autore in basso a destra.", img:"https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?w=600&q=80", imgs:["https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?w=600&q=80","https://images.unsplash.com/photo-1578321272176-b7bbc0679853?w=600&q=80","https://images.unsplash.com/photo-1544967082-d9d25d867d66?w=600&q=80"], seller:"M. Conti" },
  { id:2, cat:"Arredamento", title:"Libreria in Noce Massello", cond:"Buono", price:580, bids:12, left:"4h 52m", ts:"green", res:true, lot:false, desc:"Libreria a tre ripiani in noce massello, artigianale anni '60. 180×90×30 cm. Struttura integra.", img:"https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=600&q=80", seller:"F. Bianchi" },
  { id:3, cat:"Lotto", title:"Servizio Porcellana Limoges — 24 pz", cond:"Buono", price:210, bids:4, left:"0h 58m", ts:"red", res:false, lot:true, desc:"Servizio in porcellana Limoges, decoro floreale azzurro. 6 piatti piani, 6 fondi, 6 dessert, zuppiera, salsiera.", img:"https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=600&q=80", seller:"L. Verdi" },
  { id:4, buyNow:true, buyNowPrice:1450, cat:"Elettronica", ivaEsposta:true, regimeFiscale:"azienda", title:"Leica M6 + Summicron 50mm", cond:"Ottimo", price:1240, bids:23, left:"1g 3h", ts:"green", res:true, lot:false, desc:"Leica M6 in ottimo stato, telemetro perfetto. Include Summicron 50mm f/2, borsa originale, manuale.", img:"https://images.unsplash.com/photo-1606986628041-1f23c4c22e58?w=600&q=80", seller:"A. Rossi" },
  { id:5, cat:"Abbigliamento", title:"Cappotto Donna Cachemire Grigio", cond:"Ottimo", price:165, bids:8, left:"3h 20m", ts:"yellow", res:true, lot:false, desc:"Cappotto in puro cachemire grigio perla, taglia 42, marchio italiano, acquistato 2019.", img:"https://images.unsplash.com/photo-1591369822096-ffd140ec948f?w=600&q=80", seller:"G. Mori" },
  { id:7, cat:"Immobili", impostaImmobile:"registro", regimeFiscale:"privato", title:"Appartamento 3 locali — Milano Navigli", cond:"Ottimo", price:185000, bids:3, left:"5g 12h", ts:"green", res:true, lot:false, desc:"Appartamento di 75 mq ai Navigli, piano terzo con ascensore. 2 camere, soggiorno, cucina abitabile, bagno. Completamente ristrutturato nel 2022. Libero subito.", img:"https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?w=600&q=80", imgs:["https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?w=600&q=80","https://images.unsplash.com/photo-1484154218962-a197022b5858?w=600&q=80","https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=600&q=80","https://images.unsplash.com/photo-1522708323590-d24dbb6b0267?w=600&q=80"], matterport:"https://my.matterport.com/show/?m=SxQL3iGyvwm", seller:"G. Martinelli" },
  { id:6, cat:"Lotto", title:"Vinili Jazz — 40 LP 1960-1975", cond:"Discreto", price:290, bids:16, left:"6h 10m", ts:"green", res:false, lot:true, desc:"40 vinili jazz originali, Blue Note, Impulse!, Prestige. Condizioni variabili, copertine originali.", img:"https://images.unsplash.com/photo-1540075812090-2e2e8ace5e27?w=600&q=80", seller:"P. Ferri" },
];
const BH = [
  { u:"#U004", a:"€ 340", t:"2 min fa" },
  { u:"#U007", a:"€ 310", t:"18 min fa" },
  { u:"#U003", a:"€ 280", t:"45 min fa" },
  { u:"#U001", a:"€ 250", t:"1h 12m fa" },
];
// Generate per-item bid history with anonymous IDs
const getBids = (item) => {
  const ids = ["#U004","#U012","#U007","#U003","#U019","#U001","#U025","#U008"];
  const base = item.price;
  return Array.from({length:Math.min(item.bids,6)},(_,i)=>({
    u: ids[i],
    a: "€ " + (base - i*Math.round(base*0.05)).toLocaleString("it"),
    t: i===0?"2 min fa":i===1?"18 min fa":i===2?"45 min fa":`${i}h ${Math.round(Math.random()*50+5)}m fa`
  }));
};
const MOCK_PHOTOS = [
  "https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?w=200&q=60",
  "https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=200&q=60",
  "https://images.unsplash.com/photo-1540075812090-2e2e8ace5e27?w=200&q=60",
];

/* ─── COUNTDOWN ─── */
function useCD(init) {
  const [s, setS] = useState(init);
  useEffect(() => { const t = setInterval(() => setS(x => Math.max(0,x-1)),1000); return ()=>clearInterval(t); },[]);
  return { h:Math.floor(s/3600), m:Math.floor((s%3600)/60), s:s%60, total:s };
}
function CD({ seconds }) {
  const { h, m, s, total } = useCD(seconds);
  const col = total < 60 ? "var(--red)" : total < 600 ? "#E6A817" : "var(--warm)";
  return (
    <div className="cdw">
      {h>0&&<><div className="cdu"><span className="cdn" style={{color:col}}>{String(h).padStart(2,"0")}</span><span className="cdl">ore</span></div><span className="cds">:</span></>}
      <div className="cdu"><span className="cdn" style={{color:col}}>{String(m).padStart(2,"0")}</span><span className="cdl">min</span></div>
      <span className="cds">:</span>
      <div className="cdu"><span className="cdn" style={{color:col}}>{String(s).padStart(2,"0")}</span><span className="cdl">sec</span></div>
    </div>
  );
}

/* ─── ITEM CARD ─── */
function ItemCard({ item, onClick }) {
  const [fav, setFav] = useState(false);
  return (
    <div className="card" onClick={onClick}>
      <div className="ci">
        <img src={item.img} alt={item.title}/>
        {item.lot && <span className="cbadge">🗃 Lotto</span>}
        {item.buyNow && !item.lot && <span className="cbadge" style={{background:"var(--green)",color:"#fff",left:"auto",right:"auto",top:".7rem"}}>⚡ Compralo Subito</span>}
        <button className="cfav" onClick={e=>{e.stopPropagation();setFav(!fav);}}>{fav?"❤️":"🤍"}</button>
      </div>
      <div className="cb">
        <div className="ccat">{item.cat}</div>
        <div className="ctitle">{item.title}</div>
        <div className="cmeta">
          <div><div className="plbl">Offerta attuale</div><div className="pval"><span>€ </span>{item.price.toLocaleString("it")}</div></div>
          <div className="cbids"><strong>{item.bids}</strong><br/>offerte</div>
        </div>
        <div className="cfoot">
          <div className="ctimer">
            <div className={`tdot t${item.ts}`}></div>
            <span style={{color:item.ts==="red"?"var(--red)":item.ts==="yellow"?"#E6A817":"var(--muted)"}}>{item.left}</span>
          </div>
          <span className={`resb ${item.res?"rok":"rno"}`}>{item.res?"✓ Riserva":"✗ Riserva"}</span>
        </div>
      </div>
    </div>
  );
}

/* ─── DETAIL MODAL ─── */
function DetailModal({ item, onClose }) {
  const [bv, setBv] = useState("");
  const [ok, setOk] = useState(false);
  const [th, setTh] = useState(0);
  const [buyNowModal, setBuyNowModal] = useState(false);
  const [payMethod, setPayMethod] = useState("card");
  const [buyDone, setBuyDone] = useState(false);
  const [showBids, setShowBids] = useState(false);
  const go = () => { if(bv){setOk(true);setTimeout(()=>setOk(false),2200);setBv("");} };
  const photos = item.imgs || [item.img, item.img, item.img];
  const bids = getBids(item);

  return (
    <>
      {/* ── DETAIL OVERLAY ── */}
      <div className="ov" onClick={()=>{setShowBids(false);onClose();}}>
        <div className="modal" onClick={e=>e.stopPropagation()}>
          <div className="mhdr">
            <h2>{item.cat} — {item.title}</h2>
            <button className="mcl" onClick={onClose}>✕</button>
          </div>
          <div className="mbody">
            {/* LEFT: gallery */}
            <div>
              <img className="gmain" src={photos[th]} alt="" style={{transition:"opacity .2s"}}/>
              <div className="gthumbs">
                {photos.map((src,i)=>(
                  <img key={i} className={`gth ${th===i?"on":""}`} src={src} alt="" onClick={()=>setTh(i)}/>
                ))}
              </div>
              {/* Matterport virtual tour */}
              {item.matterport && (
                <a href={item.matterport} target="_blank" rel="noopener noreferrer"
                  style={{display:"flex",alignItems:"center",gap:".55rem",marginTop:".7rem",padding:".6rem .9rem",background:"rgba(26,77,124,.1)",border:"1px solid rgba(26,77,124,.25)",borderRadius:"2px",color:"#6aabdf",fontSize:".78rem",textDecoration:"none",fontWeight:500,transition:"background .15s"}}
                  onMouseOver={e=>e.currentTarget.style.background="rgba(26,77,124,.18)"}
                  onMouseOut={e=>e.currentTarget.style.background="rgba(26,77,124,.1)"}>
                  <span style={{fontSize:"1.1rem"}}>🏠</span>
                  <div>
                    <div style={{fontWeight:600,letterSpacing:".03em"}}>Virtual Tour 3D — Matterport</div>
                    <div style={{fontSize:".68rem",color:"rgba(100,160,210,.7)",marginTop:".1rem"}}>Esplora l'immobile in 3D prima di fare offerta</div>
                  </div>
                  <span style={{marginLeft:"auto",fontSize:".72rem",opacity:.7}}>↗</span>
                </a>
              )}
              <div style={{marginTop:"1rem",padding:".65rem .85rem",background:"var(--cream)",borderRadius:"2px",fontSize:".74rem",color:"var(--muted)"}}>
                <strong style={{color:"var(--char)"}}>Venditore:</strong> {item.seller}
                &nbsp;·&nbsp;
                <strong style={{color:"var(--char)"}}>Cond.:</strong> {item.cond}
                &nbsp;·&nbsp;
                <span style={{color:"var(--green)",fontSize:".7rem"}}>✓ Verificato</span>
              </div>
              {/* IVA / Imposta badge */}
              <div style={{marginTop:".5rem",display:"flex",flexWrap:"wrap",gap:".4rem"}}>
                {item.cat==="Immobili" ? (
                  <span style={{fontSize:".68rem",padding:".15rem .55rem",borderRadius:"1px",background:item.impostaImmobile==="iva"?"rgba(26,77,124,.12)":"rgba(200,133,42,.1)",color:item.impostaImmobile==="iva"?"#6aabdf":"var(--amber)",border:`1px solid ${item.impostaImmobile==="iva"?"rgba(26,77,124,.25)":"rgba(200,133,42,.25)"}`,letterSpacing:".05em",textTransform:"uppercase"}}>
                    {item.impostaImmobile==="iva" ? "🏢 Vendita soggetta a IVA" : "📋 Imposta di registro"}
                  </span>
                ) : (
                  <span style={{fontSize:".68rem",padding:".15rem .55rem",borderRadius:"1px",background:item.ivaEsposta?"rgba(26,77,124,.1)":"rgba(253,250,246,.06)",color:item.ivaEsposta?"#6aabdf":"var(--muted)",border:"1px solid rgba(253,250,246,.1)",letterSpacing:".05em",textTransform:"uppercase"}}>
                    {item.ivaEsposta ? "💶 IVA esposta" : "👤 Privato — senza IVA"}
                  </span>
                )}
                {item.regimeFiscale==="azienda" && <span style={{fontSize:".68rem",padding:".15rem .55rem",borderRadius:"1px",background:"rgba(253,250,246,.05)",color:"var(--muted)",border:"1px solid rgba(253,250,246,.08)",letterSpacing:".05em",textTransform:"uppercase"}}>🏢 Venditore professionale</span>}
              </div>
            </div>
            {/* RIGHT: info + bid */}
            <div>
              <div className="mcat">{item.cat}</div>
              <div className="mtitle">{item.title}</div>
              <span className="mcond">{item.cond}</span>
              <p className="mdesc">{item.desc}</p>
              <div className="bidbox">
                <div className="br">
                  <span className="bk">Offerta attuale{item.ivaEsposta ? " (IVA incl.)" : ""}</span>
                  <span className="bv">€ {item.price.toLocaleString("it")}{item.ivaEsposta ? <span style={{fontSize:".62rem",color:"var(--muted)",marginLeft:".3rem"}}>di cui IVA 22%: € {Math.round(item.price/1.22*0.22).toLocaleString("it")}</span> : ""}</span>
                </div>
                <div className="br">
                  <span className="bk">Commissione acquirente ({getRoyalty(item.cat, item.price)}%{item.cat==="Immobili" ? ` — fascia ${FASCE_IMMOBILE.find(f=>(item.price||0)<=f.max)?.label||""}` : ""})</span>
                  <span className="bv" style={{color:"var(--amber)"}}>+ € {(item.price*getRoyalty(item.cat, item.price)/100).toLocaleString("it",{maximumFractionDigits:0})}</span>
                </div>
                <div className="br">
                  <span className="bk" style={{fontWeight:600}}>Totale da pagare</span>
                  <span className="bv" style={{color:"var(--green)",fontWeight:700}}>€ {(item.price*(1+getRoyalty(item.cat, item.price)/100)).toLocaleString("it",{maximumFractionDigits:0})}</span>
                </div>
                <div className="br">
                  <span className="bk">Offerte</span>
                  <span className="bv" style={{cursor:"pointer",borderBottom:"1px dashed var(--amber)",position:"relative"}}
                    onClick={e=>{e.stopPropagation();setShowBids(v=>!v);}}>
                    {item.bids} {showBids?"▲":"▼"}
                    {showBids && (
                      <div style={{position:"absolute",right:0,top:"110%",zIndex:50,background:"var(--warm)",border:"1px solid var(--border)",borderRadius:"3px",boxShadow:"0 8px 32px rgba(28,26,23,.18)",minWidth:"260px",padding:".7rem 0"}}
                        onClick={e=>e.stopPropagation()}>
                        <div style={{padding:".3rem 1rem .6rem",fontSize:".62rem",letterSpacing:".1em",textTransform:"uppercase",color:"var(--muted)",borderBottom:"1px solid var(--border)",marginBottom:".4rem"}}>
                          Storico offerte — ID utente anonimizzato
                        </div>
                        {bids.map((b,i)=>(
                          <div key={i} style={{display:"flex",alignItems:"center",justifyContent:"space-between",padding:".38rem 1rem",fontSize:".78rem",background:i===0?"rgba(200,133,42,.06)":"transparent"}}>
                            <span style={{fontFamily:"monospace",color:i===0?"var(--amber)":"var(--muted)",fontSize:".72rem"}}>{b.u}</span>
                            <span style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1rem",fontWeight:i===0?600:400,color:i===0?"var(--amber)":"var(--char)"}}>{b.a}</span>
                            <span style={{fontSize:".68rem",color:"var(--muted)"}}>{b.t}</span>
                          </div>
                        ))}
                        {item.bids > 6 && <div style={{padding:".4rem 1rem 0",fontSize:".7rem",color:"var(--muted)",textAlign:"center"}}>+{item.bids-6} offerte precedenti</div>}
                      </div>
                    )}
                  </span>
                </div>
                <div className="br"><span className="bk">Scade tra</span><span className="bv">{item.left}</span></div>
              </div>
              {/* CAUZIONE */}
              <div className="caubox">
                🔐 <strong>Cauzione richiesta: € {calcCauzione(item.price).toLocaleString("it")}</strong>
                <span style={{fontSize:".72rem",color:"var(--muted)",marginLeft:".4rem"}}>({cauzioneLabel()})</span><br/>
                <span style={{fontSize:".74rem",color:"var(--muted)"}}>
                  Da versare per essere abilitato a fare offerte. Restituita integralmente se non risulti aggiudicatario.
                  {item.cat==="Immobili" && " Per gli immobili la cauzione viene trattenuta a titolo di caparra in caso di aggiudicazione."}
                </span>
                <div style={{marginTop:".55rem"}}>
                  <button style={{fontSize:".72rem",background:"var(--green)",color:"#fff",border:"none",padding:".28rem .8rem",borderRadius:"2px",cursor:"pointer",fontFamily:"'DM Sans',sans-serif",letterSpacing:".05em"}}>
                    💳 Versa cauzione e partecipa
                  </button>
                </div>
              </div>
              <div className="resind">
                <div className="rsdot" style={{background:item.res?"var(--green)":"var(--red)"}}></div>
                <span style={{color:item.res?"var(--green)":"var(--red)",fontSize:".78rem"}}>
                  Riserva: {item.res ? "raggiunta ✓" : "non raggiunta — l'asta potrebbe non concludersi"}
                </span>
              </div>
              {/* Bid form */}
              <div className="bform">
                <input className="bin" type="number" placeholder={`Min. € ${item.price+10}`} value={bv} onChange={e=>setBv(e.target.value)}/>
                <button className="bsub" onClick={go}>{ok?"✓ Inviata!":"Fai offerta"}</button>
              </div>
              {/* Compralo Subito box */}
              {item.buyNow && (
                <div style={{marginTop:".8rem",background:"rgba(45,106,79,.06)",border:"1px solid rgba(45,106,79,.2)",borderRadius:"2px",padding:".85rem 1rem"}}>
                  <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"var(--green)",marginBottom:".4rem"}}>⚡ Compralo Subito disponibile</div>
                  <div style={{display:"flex",alignItems:"center",justifyContent:"space-between",gap:"1rem",flexWrap:"wrap"}}>
                    <div>
                      <div style={{fontSize:".62rem",color:"var(--muted)"}}>Prezzo fisso</div>
                      <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.5rem",fontWeight:600,color:"var(--green)"}}>€ {item.buyNowPrice?.toLocaleString("it")}</div>
                      <div style={{fontSize:".68rem",color:"var(--muted)",marginTop:".15rem"}}>
                        + {getRoyalty(item.cat, item.buyNowPrice)}% = € {Math.round(item.buyNowPrice*(1+getRoyalty(item.cat, item.buyNowPrice)/100)).toLocaleString("it")} totale
                      </div>
                    </div>
                    <button
                      style={{background:"var(--green)",color:"#fff",border:"none",padding:".6rem 1.4rem",borderRadius:"2px",fontFamily:"'DM Sans',sans-serif",fontSize:".78rem",letterSpacing:".06em",textTransform:"uppercase",cursor:"pointer",whiteSpace:"nowrap"}}
                      onClick={e=>{e.stopPropagation();setBuyNowModal(true);}}>
                      ⚡ Acquista ora
                    </button>
                  </div>
                  <div style={{fontSize:".68rem",color:"var(--muted)",marginTop:".5rem"}}>💳 Bonifico · Carta · PayPal</div>
                </div>
              )}
              {/* Storico live sotto form offerta */}
              <div style={{marginTop:".9rem",fontSize:".72rem",color:"var(--muted)",textAlign:"center"}}>
                💡 Clicca sul numero delle offerte per vedere lo storico dettagliato
              </div>
            </div>
          </div>
        </div>
      </div>

      {/* ── COMPRALO SUBITO PAYMENT MODAL ── */}
      {buyNowModal && (
        <div style={{position:"fixed",inset:0,zIndex:400,background:"rgba(28,26,23,.85)",display:"flex",alignItems:"center",justifyContent:"center",padding:"1rem"}}
          onClick={()=>setBuyNowModal(false)}>
          <div style={{background:"var(--warm)",borderRadius:"4px",maxWidth:"480px",width:"100%",overflow:"hidden",maxHeight:"90vh",overflowY:"auto"}}
            onClick={e=>e.stopPropagation()}>
            {!buyDone ? (
              <>
                <div className="mhdr">
                  <h2 style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.15rem"}}>⚡ Compralo Subito — {item.title}</h2>
                  <button className="mcl" onClick={()=>setBuyNowModal(false)}>✕</button>
                </div>
                <div style={{padding:"1.4rem"}}>
                  {/* Riepilogo costi */}
                  <div style={{background:"var(--cream)",border:"1px solid var(--border)",borderRadius:"2px",padding:".9rem 1rem",marginBottom:"1.2rem",fontSize:".82rem",lineHeight:1.8}}>
                    <div style={{display:"flex",justifyContent:"space-between"}}><span>Prezzo oggetto</span><strong>€ {item.buyNowPrice?.toLocaleString("it")}</strong></div>
                    <div style={{display:"flex",justifyContent:"space-between",color:"var(--muted)"}}><span>🔐 Cauzione ({cauzioneLabel()})</span><span>€ {calcCauzione(item.buyNowPrice).toLocaleString("it")} <span style={{fontSize:".68rem"}}>(inclusa nel totale)</span></span></div>
                    <div style={{display:"flex",justifyContent:"space-between"}}><span>Commissione Battilo ({getRoyalty(item.cat, item.buyNowPrice)}%{item.cat==="Immobili"?" — fascia prezzo":""})</span><span style={{color:"var(--amber)"}}>+ € {Math.round(item.buyNowPrice*getRoyalty(item.cat, item.buyNowPrice)/100).toLocaleString("it")}</span></div>
                    <div style={{display:"flex",justifyContent:"space-between",borderTop:"1px solid var(--border)",paddingTop:".5rem",marginTop:".5rem"}}>
                      <strong>Totale da pagare</strong>
                      <strong style={{color:"var(--green)",fontSize:"1.05rem"}}>€ {Math.round(item.buyNowPrice*(1+getRoyalty(item.cat, item.buyNowPrice)/100)).toLocaleString("it")}</strong>
                    </div>
                  </div>
                  {/* Metodo pagamento */}
                  <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"var(--muted)",marginBottom:".75rem"}}>Scegli metodo di pagamento</div>
                  {[
                    ["card","💳 Carta di credito / debito","Visa, Mastercard, American Express"],
                    ["paypal","🅿 PayPal","Paga con il tuo conto PayPal"],
                    ["bank","🏦 Bonifico bancario","Riceverai le coordinate IBAN via email"]
                  ].map(([v,label,sub])=>(
                    <label key={v} style={{display:"flex",alignItems:"flex-start",gap:".65rem",cursor:"pointer",padding:".65rem .9rem",border:`1px solid ${payMethod===v?"var(--amber)":"var(--border)"}`,background:payMethod===v?"var(--amber-p)":"var(--cream)",borderRadius:"2px",marginBottom:".5rem",transition:"all .15s"}}>
                      <input type="radio" name="battilo_pay" value={v} checked={payMethod===v} onChange={()=>setPayMethod(v)} style={{accentColor:"var(--amber)",marginTop:".15rem",flexShrink:0}}/>
                      <div>
                        <div style={{fontSize:".84rem",fontWeight:500}}>{label}</div>
                        <div style={{fontSize:".72rem",color:"var(--muted)"}}>{sub}</div>
                      </div>
                    </label>
                  ))}
                  {/* Form carta */}
                  {payMethod==="card" && (
                    <div style={{marginTop:".9rem",padding:"1rem",border:"1px solid var(--border)",borderRadius:"2px",background:"var(--cream)"}}>
                      <div className="fg"><label className="fl">Numero carta</label><input className="fi" placeholder="1234 5678 9012 3456"/></div>
                      <div className="frow">
                        <div className="fg"><label className="fl">Scadenza</label><input className="fi" placeholder="MM/AA"/></div>
                        <div className="fg"><label className="fl">CVV</label><input className="fi" placeholder="123"/></div>
                      </div>
                    </div>
                  )}
                  {/* Bonifico */}
                  {payMethod==="bank" && (
                    <div style={{marginTop:".9rem",padding:"1rem",border:"1px solid rgba(45,106,79,.2)",borderRadius:"2px",background:"rgba(45,106,79,.04)",fontSize:".8rem",lineHeight:1.75}}>
                      🏦 <strong>Dati bancari del venditore:</strong><br/>
                      IBAN: <strong>IT60 X0542 8111 0100 0001 2345 6</strong><br/>
                      Intestatario: <strong>{item.seller}</strong><br/>
                      Causale: <strong>Battilo #{item.id} — {item.title}</strong><br/>
                      <span style={{color:"var(--muted)",fontSize:".72rem"}}>Completa il bonifico entro 48h. La spedizione avviene dopo la conferma di avvenuta consegna.</span>
                    </div>
                  )}
                  {/* PayPal */}
                  {payMethod==="paypal" && (
                    <div style={{marginTop:".9rem",padding:"1rem",border:"1px solid rgba(26,77,124,.2)",borderRadius:"2px",background:"rgba(26,77,124,.04)",fontSize:".82rem",textAlign:"center"}}>
                      🅿 Verrai reindirizzato a PayPal per completare il pagamento in sicurezza.
                    </div>
                  )}
                  <button
                    style={{width:"100%",marginTop:"1.2rem",background:"var(--green)",color:"#fff",border:"none",padding:".75rem",borderRadius:"2px",fontFamily:"'DM Sans',sans-serif",fontSize:".85rem",letterSpacing:".07em",textTransform:"uppercase",cursor:"pointer"}}
                    onClick={()=>setBuyDone(true)}>
                    ✅ Conferma acquisto → € {Math.round(item.buyNowPrice*(1+getRoyalty(item.cat, item.buyNowPrice)/100)).toLocaleString("it")}
                  </button>
                </div>
              </>
            ) : (
              <div style={{textAlign:"center",padding:"2.5rem 2rem"}}>
                <div style={{fontSize:"3rem",marginBottom:"1rem"}}>🎉</div>
                <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.8rem",color:"var(--green)",marginBottom:".7rem"}}>Acquisto completato!</div>
                <p style={{fontSize:".84rem",color:"var(--muted)",lineHeight:1.8,marginBottom:"1.5rem"}}>
                  Hai acquistato <strong>"{item.title}"</strong>.<br/>
                  Riceverai conferma via email con i dettagli di consegna.<br/>
                  {payMethod==="bank" && <><strong>Ricorda:</strong> completa il bonifico entro 48h.</>}
                </p>
                <button
                  style={{background:"var(--amber)",color:"#fff",border:"none",padding:".65rem 1.8rem",borderRadius:"2px",fontFamily:"'DM Sans',sans-serif",fontSize:".8rem",letterSpacing:".06em",textTransform:"uppercase",cursor:"pointer"}}
                  onClick={()=>{setBuyNowModal(false);onClose();}}>
                  Torna alla homepage
                </button>
              </div>
            )}
          </div>
        </div>
      )}
    </>
  );
}

/* ─── REGISTRATION MODAL ─── */
// Step 0 = account  |  Step 1 = documenti  |  Step 2 = indirizzo+banca  |  Step 3 = successo
function RegisterModal({ onClose, onSuccess }) {
  const [step, setStep] = useState(0);
  const [f, setF] = useState({ name:"", email:"", pwd:"", pwd2:"", isSeller:false, entityType:"privato" });
  const [sf, setSf] = useState({
    taxCode:"", iban:"", indirizzo:"", cap:"", citta:"", provincia:"",
    pec:"", sdi:"0000000",
    companyName:"", piva:"", regImprese:"",
    legalRepName:"", legalRepTaxCode:"", legalRepRole:"",
    companyPec:"", companySdi:"",
    idDoc:false, docPreview:null, docDataUrl:null, docMime:"", docFileName:"", docFileSize:"",
    visuraDoc:false, visuraDataUrl:null, visuraMime:"", visuraFileName:"", visuraFileSize:"",
    prov1:false, prov2:false, prov3:false, royalty:false
  });
  const docRef = React.useRef(null);
  const visRef = React.useRef(null);
  const upd  = (k,v) => setF(p=>({...p,[k]:v}));
  const supd = (k,v) => setSf(p=>({...p,[k]:v}));
  const isSocieta = f.entityType === "societa";

  const handleDoc = e => {
    const file = e.target.files[0]; if(!file) return;
    if(file.size > 10*1024*1024){ alert("Max 10MB"); return; }
    if(!["image/jpeg","image/png","image/jpg","application/pdf"].includes(file.type)){ alert("Usa JPG, PNG o PDF"); return; }
    const r = new FileReader();
    r.onload = ev => setSf(p=>({...p, idDoc:true, docDataUrl:ev.target.result, docMime:file.type,
      docFileName:file.name, docFileSize:(file.size/1024).toFixed(0)+"KB",
      docPreview: file.type.startsWith("image/") ? ev.target.result : null }));
    r.readAsDataURL(file);
  };
  const handleVis = e => {
    const file = e.target.files[0]; if(!file) return;
    if(file.size > 10*1024*1024){ alert("Max 10MB"); return; }
    const r = new FileReader();
    r.onload = ev => setSf(p=>({...p, visuraDoc:true, visuraDataUrl:ev.target.result,
      visuraMime:file.type, visuraFileName:file.name, visuraFileSize:(file.size/1024).toFixed(0)+"KB" }));
    r.readAsDataURL(file);
  };

  const canStep0 = !!(f.name.trim() && f.email.includes("@") && f.pwd.length>=6 && f.pwd===f.pwd2);
  // Step 1: documenti (società + venditore) — acquirente privato non ha requisiti bloccanti qui
  const canStep1 = !(
    (isSocieta && !(sf.companyName.trim() && sf.piva.trim() && sf.legalRepName.trim() && sf.legalRepTaxCode.trim() && sf.visuraDoc))
    || (f.isSeller && !(sf.idDoc && sf.prov1 && sf.prov2 && sf.prov3 && sf.royalty))
  );
  // Step 2: indirizzo obbligatorio per tutti
  const canStep2 = !!(sf.indirizzo.trim() && sf.cap.trim() && sf.citta.trim());

  const doSuccess = () => {
    onSuccess({
      name:f.name, email:f.email, isSeller:f.isSeller, entityType:f.entityType,
      taxCode: sf.taxCode||sf.legalRepTaxCode, iban:sf.iban,
      indirizzo:sf.indirizzo, cap:sf.cap, citta:sf.citta, provincia:sf.provincia,
      pec: isSocieta?sf.companyPec:sf.pec, sdi: isSocieta?sf.companySdi:sf.sdi,
      companyName:sf.companyName, piva:sf.piva, legalRepName:sf.legalRepName, legalRepRole:sf.legalRepRole,
      docFileName:sf.docFileName, docDataUrl:sf.docDataUrl, docMime:sf.docMime,
      visuraFileName:sf.visuraFileName, visuraDataUrl:sf.visuraDataUrl, visuraMime:sf.visuraMime
    });
    onClose();
  };

  /* ── STEP 3: schermata successo ── */
  if(step===3) return (
    <div className="ov" onClick={onClose}>
      <div className="lmodal" onClick={e=>e.stopPropagation()}>
        <div className="succ" style={{paddingTop:"3rem"}}>
          <div className="succicon">🎉</div>
          <div className="succtitle">Benvenuto su Battilo!</div>
          <p className="succmsg">
            Il tuo account è stato creato con successo.<br/>
            {f.isSeller ? <><strong>Account venditore attivato.</strong><br/>Il documento sarà verificato entro 24h.</> : "Puoi iniziare a fare offerte subito!"}
          </p>
          <button className="snext" onClick={doSuccess}>Accedi alla piattaforma →</button>

        </div>
      </div>
    </div>
  );

  return (
    <div className="ov" onClick={onClose}>
      <div className="lmodal" onClick={e=>e.stopPropagation()}>
        <div className="mhdr">
          <div style={{display:"flex",alignItems:"center",gap:".6rem"}}>
            <Logo size={28} textSize="1rem"/>
            <span style={{color:"var(--muted)",fontSize:".8rem",marginLeft:".3rem"}}>
              — {step===0 ? "Crea account" : step===1 ? (isSocieta ? "Verifica società" : f.isSeller ? "Documenti" : "Documenti") : "Indirizzo & Fatturazione"}
            </span>
          </div>
          <button className="mcl" onClick={onClose}>✕</button>
        </div>

        {/* ══ STEP 0 ══ */}
        {step===0 && (
          <div className="regbody">
            <div className="reg-section">
              <div className="reg-section-title">I tuoi dati</div>
              <div className="fg"><label className="fl">Nome e cognome *</label>
                <input className="fi" placeholder="Es. Marco Bianchi" value={f.name} onChange={e=>upd("name",e.target.value)}/></div>
              <div className="fg"><label className="fl">Email *</label>
                <input className="fi" type="email" placeholder="tuaemail@esempio.it" value={f.email} onChange={e=>upd("email",e.target.value)}/></div>
              <div className="frow">
                <div className="fg"><label className="fl">Password *</label>
                  <input className="fi" type="password" placeholder="Min. 6 caratteri" value={f.pwd} onChange={e=>upd("pwd",e.target.value)}/></div>
                <div className="fg"><label className="fl">Conferma password *</label>
                  <input className="fi" type="password" placeholder="Ripeti password" value={f.pwd2} onChange={e=>upd("pwd2",e.target.value)}/></div>
              </div>
              {f.pwd && f.pwd2 && f.pwd!==f.pwd2 && <p style={{fontSize:".74rem",color:"var(--red)",marginBottom:".8rem"}}>⚠ Le password non corrispondono</p>}
            </div>

            <div className="reg-section">
              <div className="reg-section-title">Tipologia</div>
              <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:".5rem",marginBottom:".9rem"}}>
                {[["privato","👤 Privato","Persona fisica"],["societa","🏢 Società / Azienda","P.IVA + legale rapp."]].map(([v,lbl,sub])=>(
                  <label key={v} style={{cursor:"pointer",border:`2px solid ${f.entityType===v?"var(--amber)":"var(--border)"}`,borderRadius:"3px",padding:".65rem .85rem",background:f.entityType===v?"var(--amber-p)":"var(--cream)",transition:"all .15s"}}>
                    <input type="radio" name="entityType" value={v} checked={f.entityType===v} onChange={()=>upd("entityType",v)} style={{display:"none"}}/>
                    <div style={{fontWeight:600,fontSize:".82rem",marginBottom:".12rem"}}>{lbl}</div>
                    <div style={{fontSize:".67rem",color:"var(--muted)"}}>{sub}</div>
                  </label>
                ))}
              </div>
              <label className="lottoggle" style={{marginBottom:".5rem"}}>
                <input type="radio" name="role" checked={!f.isSeller} onChange={()=>upd("isSeller",false)} style={{accentColor:"var(--amber)"}}/>
                <div><div className="lotlbl">🛒 Solo acquirente</div><div className="lotsub">Fai offerte. Gratuito, senza documenti aggiuntivi.</div></div>
              </label>
              <label className="lottoggle">
                <input type="radio" name="role" checked={f.isSeller} onChange={()=>upd("isSeller",true)} style={{accentColor:"var(--amber)"}}/>
                <div><div className="lotlbl">🏷 Acquirente + Venditore</div><div className="lotsub">Metti oggetti all'asta. Richiede verifica identità.</div></div>
              </label>
            </div>

            <div className="sacts">
              <span className="sprog">Passo <strong>1</strong> di 3</span>
              <button className="snext" style={{opacity:canStep0?1:.38,cursor:canStep0?"pointer":"not-allowed"}}
                onClick={()=>{ if(canStep0) setStep(1); }}>Continua →</button>
            </div>
          </div>
        )}

        {/* ══ STEP 1 — DOCUMENTI ══ */}
        {step===1 && (
          <div className="regbody">

            {/* acquirente privato: nessun doc richiesto */}
            {!f.isSeller && !isSocieta && (
              <div style={{padding:"1.2rem",background:"rgba(45,106,79,.06)",border:"1px solid rgba(45,106,79,.2)",borderRadius:"3px",marginBottom:"1.2rem",fontSize:".82rem",color:"var(--char)",lineHeight:1.75}}>
                ✅ <strong>Nessun documento richiesto</strong> per gli acquirenti privati.<br/>
                Clicca <strong>Continua</strong> per procedere.
              </div>
            )}

            {/* dati società */}
            {isSocieta && (
              <div className="reg-section">
                <div className="reg-section-title">🏢 Dati societari</div>
                <div className="fg" style={{marginBottom:".6rem"}}>
                  <label className="fl">Ragione sociale *</label>
                  <input className="fi" placeholder="Es. Rossi & Figli S.r.l." value={sf.companyName} onChange={e=>supd("companyName",e.target.value)}/>
                </div>
                <div className="frow" style={{marginBottom:".6rem"}}>
                  <div className="fg"><label className="fl">Partita IVA *</label>
                    <input className="fi" placeholder="IT12345678901" value={sf.piva} onChange={e=>supd("piva",e.target.value)} style={{fontFamily:"monospace"}}/></div>
                  <div className="fg"><label className="fl">N° REA</label>
                    <input className="fi" placeholder="MI-1234567" value={sf.regImprese} onChange={e=>supd("regImprese",e.target.value)} style={{fontFamily:"monospace"}}/></div>
                </div>
                <div className="frow" style={{marginBottom:".6rem"}}>
                  <div className="fg"><label className="fl">Nome legale rappresentante *</label>
                    <input className="fi" placeholder="Mario Rossi" value={sf.legalRepName} onChange={e=>supd("legalRepName",e.target.value)}/></div>
                  <div className="fg"><label className="fl">CF legale rapp. *</label>
                    <input className="fi" placeholder="RSSMRA70A01H501Z" value={sf.legalRepTaxCode} onChange={e=>supd("legalRepTaxCode",e.target.value)} style={{textTransform:"uppercase",fontFamily:"monospace"}}/></div>
                </div>
                <div className="fg"><label className="fl">Carica / Ruolo</label>
                  <input className="fi" placeholder="Amministratore Unico" value={sf.legalRepRole} onChange={e=>supd("legalRepRole",e.target.value)}/></div>
              </div>
            )}

            {/* documento identità — venditori e società */}
            {(f.isSeller || isSocieta) && (
              <div className="reg-section">
                <div className="reg-section-title">📄 {isSocieta?"Documento Legale Rappresentante":"Verifica identità"}</div>
                <input ref={docRef} type="file" accept=".jpg,.jpeg,.png,.pdf" style={{display:"none"}} onChange={handleDoc}/>
                <div className={`id-upload ${sf.idDoc?"done":""}`} onClick={()=>docRef.current&&docRef.current.click()}>
                  <div className="id-icon">{sf.idDoc?"✅":"🪪"}</div>
                  {sf.idDoc
                    ? <div className="id-txt ok"><strong>✅ {sf.docFileName}</strong> · {sf.docFileSize}
                        {sf.docPreview && <img src={sf.docPreview} alt="" style={{display:"block",marginTop:".5rem",maxWidth:"160px",maxHeight:"90px",objectFit:"cover",borderRadius:"2px"}}/>}
                      </div>
                    : <div className="id-txt"><strong>Clicca per allegare il documento</strong><br/>Carta d'identità, passaporto o patente · JPG, PNG, PDF · Max 10MB</div>}
                </div>
              </div>
            )}

            {/* visura — solo società */}
            {isSocieta && (
              <div className="reg-section">
                <div className="reg-section-title">📑 Visura camerale *</div>
                <input ref={visRef} type="file" accept=".jpg,.jpeg,.png,.pdf" style={{display:"none"}} onChange={handleVis}/>
                <div className={`id-upload ${sf.visuraDoc?"done":""}`} onClick={()=>visRef.current&&visRef.current.click()}>
                  <div className="id-icon">{sf.visuraDoc?"✅":"📑"}</div>
                  {sf.visuraDoc
                    ? <div className="id-txt ok"><strong>✅ {sf.visuraFileName}</strong> · {sf.visuraFileSize}</div>
                    : <div className="id-txt"><strong>Clicca per allegare la visura camerale</strong><br/>PDF o immagine · Max 10MB · non anteriore a 3 mesi</div>}
                </div>
              </div>
            )}

            {/* provenienza — solo venditori */}
            {f.isSeller && (
              <div className="reg-section">
                <div className="reg-section-title">⚖️ Responsabilità e provenienza oggetti</div>
                <div className="legal-box">
                  <h4>Dichiarazione legale obbligatoria</h4>
                  Il venditore dichiara sotto la propria responsabilità che:
                  <ul style={{marginTop:".5rem"}}>
                    <li>Gli oggetti sono di <strong>legittima proprietà</strong> o ha piena facoltà di venderli.</li>
                    <li>Gli oggetti <strong>non provengono da attività illecite</strong>, furti o ricettazione.</li>
                    <li>Le descrizioni sono <strong>veritiere e accurate</strong>.</li>
                    <li>Battilo può <strong>segnalare alle autorità</strong> comportamenti illeciti.</li>
                    <li>Il venditore si assume <strong>piena responsabilità civile e penale</strong>.</li>
                  </ul>
                </div>
                <label className="chrow"><input type="checkbox" checked={sf.prov1} onChange={e=>supd("prov1",e.target.checked)}/><span>✅ Gli oggetti sono di mia legittima proprietà o ho pieno diritto a venderli.</span></label>
                <label className="chrow"><input type="checkbox" checked={sf.prov2} onChange={e=>supd("prov2",e.target.checked)}/><span>✅ Gli oggetti <strong>non provengono da furti, ricettazione o attività illecite</strong>.</span></label>
                <label className="chrow"><input type="checkbox" checked={sf.prov3} onChange={e=>supd("prov3",e.target.checked)}/><span>✅ Ho letto e accetto il <strong style={{color:"var(--amber)"}}>Regolamento Venditori Battilo</strong>, Privacy Policy e Termini di Servizio.</span></label>
              </div>
            )}

            {/* royalty — solo venditori */}
            {f.isSeller && (
              <div className="reg-section">
                <div className="reg-section-title">💰 Commissioni acquirenti (Royalty)</div>
                <div className="royalty-info">
                  <h4>Come funzionano le commissioni su Battilo</h4>
                  Per ogni asta aggiudicata l'acquirente paga una commissione a Battilo. Il venditore riceve l'intero importo.
                  <div style={{display:"flex",gap:"1rem",margin:".6rem 0",justifyContent:"center",flexWrap:"wrap"}}>
                    <div style={{textAlign:"center",padding:".6rem 1.2rem",background:"rgba(200,133,42,.08)",borderRadius:"2px",minWidth:"120px"}}>
                      <div style={{fontSize:".65rem",textTransform:"uppercase",color:"var(--muted)",marginBottom:".2rem"}}>Beni mobili</div>
                      <span className="royalty-pct" style={{fontSize:"1.8rem"}}>{ROYALTY_MOBILE}%</span>
                    </div>
                    <div style={{background:"rgba(26,77,124,.06)",border:"1px solid rgba(26,77,124,.15)",borderRadius:"2px",padding:".6rem .9rem",minWidth:"170px"}}>
                      <div style={{fontSize:".65rem",textTransform:"uppercase",color:"var(--muted)",marginBottom:".45rem"}}>🏠 Immobili — per fascia</div>
                      {FASCE_IMMOBILE.map(fi=>(
                        <div key={fi.label} style={{display:"flex",justifyContent:"space-between",gap:"1rem",fontSize:".7rem",lineHeight:1.9,borderBottom:"1px solid rgba(26,77,124,.08)"}}>
                          <span style={{color:"var(--muted)"}}>{fi.label}</span><strong style={{color:"#4a90c4"}}>{fi.pct}%</strong>
                        </div>
                      ))}
                    </div>
                  </div>
                </div>
                <label className="chrow"><input type="checkbox" checked={sf.royalty} onChange={e=>supd("royalty",e.target.checked)}/><span>✅ Prendo atto: acquirenti pagano <strong>{ROYALTY_MOBILE}% beni mobili</strong> e <strong>2–4% immobili</strong> di commissione aggiuntiva.</span></label>
              </div>
            )}

            <div className="sacts">
              <button className="sback" onClick={()=>setStep(0)}>← Indietro</button>
              <div style={{display:"flex",alignItems:"center",gap:"1rem"}}>
                <span className="sprog">Passo <strong>2</strong> di 3</span>
                <button className="snext" style={{opacity:canStep1?1:.38,cursor:canStep1?"pointer":"not-allowed"}}
                  onClick={()=>{ if(canStep1) setStep(2); }}>Continua →</button>
              </div>
            </div>
          </div>
        )}

        {/* ══ STEP 2 — INDIRIZZO & BANCA ══ */}
        {step===2 && (
          <div className="regbody">

            {/* ── INDIRIZZO — TUTTI ── */}
            <div className="reg-section">
              <div className="reg-section-title">🏠 {isSocieta?"Sede legale":"Residenza / Domicilio fiscale"}</div>
              {!isSocieta && (
                <div className="fg" style={{marginBottom:".6rem"}}>
                  <label className="fl">Codice fiscale *</label>
                  <input className="fi" placeholder="RSSMRC85M01H501Z" value={sf.taxCode} onChange={e=>supd("taxCode",e.target.value)} style={{textTransform:"uppercase",fontFamily:"monospace"}}/>
                </div>
              )}
              <div className="fg" style={{marginBottom:".6rem"}}>
                <label className="fl">Indirizzo (via, n° civico) *</label>
                <input className="fi" placeholder="Via Roma 15" value={sf.indirizzo} onChange={e=>supd("indirizzo",e.target.value)}/>
              </div>
              <div className="frow">
                <div className="fg" style={{flex:"0 0 90px"}}><label className="fl">CAP *</label>
                  <input className="fi" placeholder="20100" value={sf.cap} onChange={e=>supd("cap",e.target.value)} style={{fontFamily:"monospace"}}/></div>
                <div className="fg"><label className="fl">Città *</label>
                  <input className="fi" placeholder="Milano" value={sf.citta} onChange={e=>supd("citta",e.target.value)}/></div>
                <div className="fg" style={{flex:"0 0 70px"}}><label className="fl">Prov.</label>
                  <input className="fi" placeholder="MI" maxLength={2} value={sf.provincia} onChange={e=>supd("provincia",e.target.value.toUpperCase())} style={{textTransform:"uppercase"}}/></div>
              </div>
            </div>

            {/* ── IBAN + PEC + SDI — TUTTI ── */}
            <div className="reg-section">
              <div className="reg-section-title">🏦 Banca & Fatturazione elettronica</div>
              <div className="fg" style={{marginBottom:".7rem"}}>
                <label className="fl">IBAN per accredito pagamenti</label>
                <input className="fi" placeholder="IT60 X054 2811 1010 0000 0123 456" value={sf.iban} onChange={e=>supd("iban",e.target.value)} style={{fontFamily:"monospace"}}/>
              </div>
              <div className="frow">
                <div className="fg"><label className="fl">PEC {isSocieta?"aziendale":"(facoltativa)"}</label>
                  <input className="fi" placeholder={isSocieta?"azienda@pec.it":"nome@pec.it"} value={isSocieta?sf.companyPec:sf.pec} onChange={e=>supd(isSocieta?"companyPec":"pec",e.target.value)}/></div>
                <div className="fg">
                  <label className="fl">Codice SDI {isSocieta?"*":"(destinatario)"}</label>
                  <input className="fi" placeholder={isSocieta?"AB1C23D":"0000000"} maxLength={7} value={isSocieta?sf.companySdi:sf.sdi} onChange={e=>supd(isSocieta?"companySdi":"sdi",e.target.value.toUpperCase())} style={{fontFamily:"monospace",letterSpacing:".08em"}}/>
                  <span style={{fontSize:".65rem",color:"var(--muted)",marginTop:".25rem",display:"block"}}>{isSocieta?"7 caratteri obbligatori per B2B":"Per privati senza SDI usa 0000000"}</span>
                </div>
              </div>
            </div>

            <div className="sacts">
              <button className="sback" onClick={()=>setStep(1)}>← Indietro</button>
              <div style={{display:"flex",alignItems:"center",gap:"1rem"}}>
                <span className="sprog">Passo <strong>3</strong> di 3</span>
                <button className="snext" style={{opacity:canStep2?1:.38,cursor:canStep2?"pointer":"not-allowed"}}
                  onClick={()=>{ if(canStep2) setStep(3); }}>{f.isSeller?"Completa registrazione →":"Crea account →"}</button>
              </div>
            </div>
          </div>
        )}

      </div>
    </div>
  );
}



/* ─── SELL MODAL ─── */
const SELL_STEPS = ["Oggetto","Foto","Asta & Pagamento","Anteprima"];
function SellModal({ user, onClose }) {
  const [step, setStep] = useState(0);
  const [f, setF] = useState({ title:"", cat:"Arte", cond:"Ottimo", desc:"", base:"", reserve:"", start:"", end:"", step:"10", lot:false, lotName:"", lotEx:"", photos:[], terms:false, comm:false, provenance:false, buyNow:false, buyNowPrice:"", payBonificoEnabled:true, payCardEnabled:true, payPaypalEnabled:true, ibanVend:"", intestatario:"", ivaEsposta:false, regimeFiscale:"privato", impostaImmobile:"registro", photoService:"self", photoServiceNote:"" });
  const upd = (k,v) => setF(p=>({...p,[k]:v}));
  const addPhoto = () => { if(f.photos.length<10) upd("photos",[...f.photos, MOCK_PHOTOS[f.photos.length%3]]); };
  const delPhoto = i => upd("photos",f.photos.filter((_,j)=>j!==i));
  const royaltyEst = f.base ? (parseFloat(f.base) * getRoyalty(f.cat, f.base) / 100).toFixed(2) : null;
  const canNext = () => {
    if(step===0) return f.title.trim() && f.desc.trim() && f.provenance;
    if(step===1) return f.photos.length>=1 || f.photoService!=="self";
    if(step===2) return f.base && f.reserve && f.start && f.end && f.terms && f.comm && (!f.buyNow || f.buyNowPrice);
    return true;
  };
  if(step===4) return (
    <div className="ov" onClick={onClose}>
      <div className="smodal" onClick={e=>e.stopPropagation()}>
        <div className="succ">
          <div className="succicon">🎉</div>
          <div className="succtitle">Asta pubblicata!</div>
          <p className="succmsg"><strong>"{f.title||"Il tuo oggetto"}"</strong> è in attesa di revisione.<br/>Riceverai conferma via email entro 24 ore.<br/>Riceverai l'intero importo — commissione {getRoyalty(f.cat, f.base)}% {f.cat==="Immobili" ? "(tariffa immobili)" : ""} a carico dell'acquirente.</p>
          <button className="snext" onClick={onClose}>Torna alla homepage</button>
        </div>
      </div>
    </div>
  );
  return (
    <div className="ov" onClick={onClose}>
      <div className="smodal" onClick={e=>e.stopPropagation()}>
        <div className="mhdr">
          <h2 style={{fontFamily:"'Cormorant Garamond',serif",fontWeight:500}}>Metti in vendita</h2>
          <button className="mcl" onClick={onClose}>✕</button>
        </div>
        <div className="ssteps">{SELL_STEPS.map((s,i)=><div key={s} className={`ss ${i<step?"done":""} ${i===step?"act":""}`}>{i<step?"✓ ":""}{s}</div>)}</div>

        {step===0 && <div className="sbody">
          <div className="stitle">Descrivi il tuo oggetto</div>
          <p className="ssub">Una descrizione accurata aumenta le offerte. Sii preciso su materiali, dimensioni, condizioni.</p>
          {/* DICHIARAZIONE PROVENIENZA nel form inserimento */}
          <div className="warn-box" style={{marginBottom:"1.1rem"}}>
            ⚖️ <strong>Dichiarazione di provenienza obbligatoria</strong><br/>
            Prima di inserire l'oggetto, conferma di essere il legittimo proprietario e che l'oggetto non proviene da attività illecite.
          </div>
          <label className="chrow" style={{marginBottom:"1.2rem"}}>
            <input type="checkbox" checked={f.provenance} onChange={e=>upd("provenance",e.target.checked)}/>
            <span>✅ Confermo che questo oggetto è di mia legittima proprietà, non proviene da furti o attività illecite e mi assumo piena responsabilità sulla sua provenienza.</span>
          </label>
          <div className="fg"><label className="fl">Titolo *</label><input className="fi" placeholder="Es. Sedia Thonet originale anni '50" value={f.title} onChange={e=>upd("title",e.target.value)}/></div>
          <div className="frow">
            <div className="fg"><label className="fl">Categoria *</label><select className="fi" value={f.cat} onChange={e=>upd("cat",e.target.value)}>{["Arte","Arredamento","Elettronica","Abbigliamento","Immobili","Gioielli","Libri","Vintage","Altro"].map(c=><option key={c}>{c}</option>)}</select></div>
            <div className="fg"><label className="fl">Condizioni *</label><select className="fi" value={f.cond} onChange={e=>upd("cond",e.target.value)}>{["Ottimo","Buono","Discreto","Da restaurare"].map(c=><option key={c}>{c}</option>)}</select></div>
          </div>
          <div className="fg"><label className="fl">Descrizione dettagliata *</label><textarea className="fi" rows="4" placeholder="Materiali, dimensioni, età, provenienza, eventuali difetti da dichiarare..." value={f.desc} onChange={e=>upd("desc",e.target.value)}/></div>
          {/* ── REGIME IVA ── */}
          <div style={{borderTop:"1px solid var(--border)",paddingTop:"1rem",marginTop:".5rem",marginBottom:".8rem"}}>
            <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"var(--muted)",marginBottom:".75rem"}}>🧾 Regime fiscale e IVA</div>
            <div className="frow" style={{marginBottom:".7rem"}}>
              <div className="fg">
                <label className="fl">Sei un privato o un'azienda?</label>
                <select className="fi" value={f.regimeFiscale} onChange={e=>upd("regimeFiscale",e.target.value)}>
                  <option value="privato">👤 Privato — vendita senza IVA</option>
                  <option value="azienda">🏢 Azienda / professionista con P.IVA</option>
                </select>
              </div>
              {f.regimeFiscale==="azienda" && f.cat!=="Immobili" && (
                <div className="fg" style={{display:"flex",alignItems:"center",gap:".8rem",paddingTop:"1.4rem"}}>
                  <label style={{display:"flex",alignItems:"center",gap:".5rem",cursor:"pointer",fontSize:".82rem",color:"var(--char)"}}>
                    <input type="checkbox" checked={f.ivaEsposta} onChange={e=>upd("ivaEsposta",e.target.checked)} style={{accentColor:"var(--amber)"}}/>
                    <span>💶 Prezzo con <strong>IVA esposta</strong> (il prezzo base include IVA al 22%)</span>
                  </label>
                </div>
              )}
            </div>
            {f.cat==="Immobili" && (
              <div className="fg">
                <label className="fl">Regime fiscale per la vendita immobiliare</label>
                <select className="fi" value={f.impostaImmobile} onChange={e=>upd("impostaImmobile",e.target.value)}>
                  <option value="registro">📋 Imposta di registro (privato o esenzione IVA)</option>
                  <option value="iva">🏢 Vendita soggetta a IVA (impresa costruttrice / ristrutturatrice)</option>
                </select>
                <span style={{fontSize:".7rem",color:"var(--muted)",marginTop:".3rem",display:"block",lineHeight:1.6}}>
                  {f.impostaImmobile==="registro"
                    ? "Imposta di registro: 2% prima casa / 9% seconda casa (min. € 1.000) + imposte ipotecaria e catastale fisse."
                    : "IVA al 4% (prima casa agevolata) o 10% / 22% per altre tipologie — secondo normativa DPR 633/72."}
                </span>
              </div>
            )}
          </div>

          <label className="lottoggle">
            <input type="checkbox" checked={f.lot} onChange={e=>upd("lot",e.target.checked)}/>
            <div><div className="lotlbl">🗃 Aggiungi a un lotto</div><div className="lotsub">Vendi più oggetti insieme come un unico lotto</div></div>
          </label>
          {f.lot && <div className="frow">
            <div className="fg"><label className="fl">Nome nuovo lotto</label><input className="fi" placeholder="Es. Set cucina anni '70" value={f.lotName} onChange={e=>upd("lotName",e.target.value)}/></div>
            <div className="fg"><label className="fl">Oppure aggiungi a lotto esistente</label><select className="fi" value={f.lotEx} onChange={e=>upd("lotEx",e.target.value)}><option value="">— Seleziona —</option><option>Servizio tavola Limoges</option><option>Vinili Jazz collection</option></select></div>
          </div>}
        </div>}

        {step===1 && <div className="sbody">
          <div className="stitle">Foto & Media</div>
          <p className="ssub">Carica le foto del tuo oggetto.{f.cat==="Immobili" ? " Per gli immobili puoi affidarti al nostro servizio fotografico professionale o al Virtual Tour 3D Matterport." : ""}</p>

          {/* ── SCELTA MODALITÀ ── */}
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:".65rem",marginBottom:"1.3rem"}}>
            {/* Autonomo */}
            <label style={{cursor:"pointer",border:`2px solid ${f.photoService==="self"?"var(--amber)":"var(--border)"}`,borderRadius:"3px",padding:"1rem",background:f.photoService==="self"?"var(--amber-p)":"var(--cream)",transition:"all .18s"}}>
              <input type="radio" name="photoService" value="self" checked={f.photoService==="self"} onChange={()=>upd("photoService","self")} style={{display:"none"}}/>
              <div style={{fontSize:"1.5rem",marginBottom:".4rem"}}>📷</div>
              <div style={{fontWeight:600,fontSize:".85rem",marginBottom:".2rem"}}>Carico io le foto</div>
              <div style={{fontSize:".72rem",color:"var(--muted)",lineHeight:1.6}}>Autonomo e gratuito.<br/>Min. 1 — max 10 foto.</div>
              {f.photoService==="self" && <div style={{marginTop:".5rem",fontSize:".68rem",color:"var(--amber)",fontWeight:600}}>✓ Selezionato</div>}
            </label>


            {/* Servizio foto immobili */}
            {f.cat==="Immobili" && FOTO_SERVICE_ENABLED && (<>
              <label style={{cursor:"pointer",border:`2px solid ${f.photoService==="foto_imm"?"var(--amber)":"var(--border)"}`,borderRadius:"3px",padding:"1rem",background:f.photoService==="foto_imm"?"var(--amber-p)":"var(--cream)",transition:"all .18s"}}>
                <input type="radio" name="photoService" value="foto_imm" checked={f.photoService==="foto_imm"} onChange={()=>upd("photoService","foto_imm")} style={{display:"none"}}/>
                <div style={{fontSize:"1.5rem",marginBottom:".4rem"}}>🏠📸</div>
                <div style={{fontWeight:600,fontSize:".85rem",marginBottom:".2rem"}}>Foto immobile professionale</div>
                <div style={{fontSize:".72rem",color:"var(--muted)",lineHeight:1.6}}>Reportage fotografico completo interno/esterno. Post-produzione HDR.</div>
                <div style={{marginTop:".5rem",fontFamily:"'Cormorant Garamond',serif",fontSize:"1.05rem",color:"var(--amber)",fontWeight:600}}>€ {FOTO_IMMOBILE_PRICE}</div>
                {f.photoService==="foto_imm" && <div style={{marginTop:".3rem",fontSize:".68rem",color:"var(--amber)",fontWeight:600}}>✓ Selezionato</div>}
              </label>
              <label style={{cursor:"pointer",border:`2px solid ${f.photoService==="tour"?"var(--amber)":"var(--border)"}`,borderRadius:"3px",padding:"1rem",background:f.photoService==="tour"?"var(--amber-p)":"var(--cream)",transition:"all .18s"}}>
                <input type="radio" name="photoService" value="tour" checked={f.photoService==="tour"} onChange={()=>upd("photoService","tour")} style={{display:"none"}}/>
                <div style={{fontSize:"1.5rem",marginBottom:".4rem"}}>🏠🔮</div>
                <div style={{fontWeight:600,fontSize:".85rem",marginBottom:".2rem"}}>Virtual Tour 3D Matterport</div>
                <div style={{fontSize:".72rem",color:"var(--muted)",lineHeight:1.6}}>Scansione 3D completa dell'immobile. Tour virtuale interattivo online.</div>
                <div style={{marginTop:".5rem",fontFamily:"'Cormorant Garamond',serif",fontSize:"1.05rem",color:"var(--amber)",fontWeight:600}}>€ {VIRTUAL_TOUR_PRICE}</div>
                {f.photoService==="tour" && <div style={{marginTop:".3rem",fontSize:".68rem",color:"var(--amber)",fontWeight:600}}>✓ Selezionato</div>}
              </label>
              <label style={{cursor:"pointer",border:`2px solid ${f.photoService==="bundle"?"var(--amber)":"var(--border)"}`,borderRadius:"3px",padding:"1rem",background:f.photoService==="bundle"?"rgba(200,133,42,.12)":"var(--cream)",gridColumn:"1/-1",transition:"all .18s",position:"relative",overflow:"hidden"}}>
                <div style={{position:"absolute",top:"0",right:"0",background:"var(--amber)",color:"#fff",fontSize:".6rem",padding:".2rem .7rem",letterSpacing:".08em",textTransform:"uppercase"}}>Risparmia € {(FOTO_IMMOBILE_PRICE+VIRTUAL_TOUR_PRICE-FOTO_BUNDLE_PRICE)}</div>
                <input type="radio" name="photoService" value="bundle" checked={f.photoService==="bundle"} onChange={()=>upd("photoService","bundle")} style={{display:"none"}}/>
                <div style={{display:"flex",alignItems:"center",gap:".8rem",flexWrap:"wrap"}}>
                  <div style={{fontSize:"1.8rem"}}>🏠✨</div>
                  <div style={{flex:1}}>
                    <div style={{fontWeight:600,fontSize:".88rem",marginBottom:".15rem"}}>Bundle: Foto professionale + Virtual Tour 3D</div>
                    <div style={{fontSize:".72rem",color:"var(--muted)"}}>Reportage fotografico completo + scansione Matterport. Soluzione all-in-one per la massima visibilità.</div>
                  </div>
                  <div style={{textAlign:"right"}}>
                    <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.3rem",color:"var(--amber)",fontWeight:600}}>€ {FOTO_BUNDLE_PRICE}</div>
                    <div style={{fontSize:".65rem",color:"var(--muted)",textDecoration:"line-through"}}>€ {FOTO_IMMOBILE_PRICE+VIRTUAL_TOUR_PRICE}</div>
                  </div>
                </div>
                {f.photoService==="bundle" && <div style={{marginTop:".5rem",fontSize:".68rem",color:"var(--amber)",fontWeight:600}}>✓ Selezionato</div>}
              </label>
            </>)}
          </div>

          {/* Nota per il servizio */}
          {f.photoService!=="self" && (
            <div style={{marginBottom:"1rem"}}>
              <label className="fl">Note per il fotografo (indirizzo, disponibilità, accessi, ecc.)</label>
              <textarea className="fi" rows="2" placeholder="Es. Milano, via Brera 12 — disponibile lunedì e mercoledì pomeriggio. Citofono Rossi." value={f.photoServiceNote} onChange={e=>upd("photoServiceNote",e.target.value)}/>
              <div style={{marginTop:".5rem",padding:".65rem .9rem",background:"rgba(200,133,42,.07)",border:"1px solid rgba(200,133,42,.18)",borderRadius:"2px",fontSize:".74rem",color:"var(--muted)",lineHeight:1.7}}>
                📅 Dopo la pubblicazione dell'annuncio ti contatteremo per concordare la data del servizio. Il costo verrà addebitato separatamente.<br/>
                {f.photoService==="tour"||f.photoService==="bundle" ? "🔮 Il virtual tour Matterport sarà disponibile online entro 48h dalla scansione." : ""}
              </div>
            </div>
          )}

          {/* Upload autonomo */}
          {f.photoService==="self" && <>
            <div className="upzone" onClick={addPhoto}>
              <div className="upicon">📷</div>
              <div className="uptxt"><strong>Clicca per aggiungere foto</strong><br/>JPG, PNG · Max 5MB · {f.photos.length}/10</div>
            </div>
            {f.photos.length>0 && <div className="upprev">
              {f.photos.map((src,i)=>(
                <div key={i} className="upprevit">
                  <img src={src} alt=""/>
                  {i===0 && <span style={{position:"absolute",bottom:"-7px",left:"50%",transform:"translateX(-50%)",background:"var(--amber)",color:"#fff",fontSize:".5rem",padding:"1px 5px",borderRadius:"1px",whiteSpace:"nowrap"}}>Principale</span>}
                  <button className="updel" onClick={()=>delPhoto(i)}>✕</button>
                </div>
              ))}
            </div>}
          </>}
        </div>}

        {step===2 && <div className="sbody">
          <div className="stitle">Impostazioni asta</div>
          <p className="ssub">Il prezzo di riserva è la cifra minima che accetti. Se non raggiunto, l'asta non viene finalizzata.</p>
          <div className="frow">
            <div className="fg"><label className="fl">Prezzo base (€) *</label><input className="fi" type="number" placeholder="Es. 50" value={f.base} onChange={e=>upd("base",e.target.value)}/></div>
            <div className="fg"><label className="fl">Incremento minimo (€)</label><input className="fi" type="number" placeholder="10" value={f.step} onChange={e=>upd("step",e.target.value)}/></div>
          </div>
          <div className="resnote">🔒 <strong>Prezzo di riserva</strong> — Soglia minima accettabile. Se non raggiunta, <strong>l'asta non si conclude</strong>. Visibile solo a te.</div>
          <div className="fg"><label className="fl">🔒 Prezzo di riserva (€) * — privato</label><input className="fi" type="number" placeholder="Es. 200" style={{borderColor:"rgba(200,133,42,.5)",background:"rgba(200,133,42,.04)"}} value={f.reserve} onChange={e=>upd("reserve",e.target.value)}/></div>
          <div className="frow">
            <div className="fg"><label className="fl">Data/ora inizio *</label><input className="fi" type="datetime-local" value={f.start} onChange={e=>upd("start",e.target.value)}/></div>
            <div className="fg"><label className="fl">Data/ora fine *</label><input className="fi" type="datetime-local" value={f.end} onChange={e=>upd("end",e.target.value)}/></div>
          </div>
          {/* CAUZIONE INFO VENDITORE */}
          <div className="caubox" style={{marginBottom:".85rem"}}>
            🔐 <strong>Cauzione per i partecipanti: {CAUZIONE_MODE==="pct" ? `${CAUZIONE_PCT}% del prezzo base` : `€ ${CAUZIONE_FIXED}`}</strong><br/>
            <span style={{fontSize:".74rem",color:"var(--muted)"}}>
              Gli acquirenti dovranno versare una cauzione prima di fare offerte. Viene restituita a chi non risulta aggiudicatario.
              La cauzione è configurabile dall'amministratore della piattaforma.
            </span>
          </div>
          {/* RIEPILOGO ROYALTY */}
          <div className="roybox">
            💰 <strong>Commissione Battilo: {getRoyalty(f.cat, f.base)}%</strong>{f.cat==="Immobili" ? <span style={{background:"rgba(26,77,124,.1)",color:"#4a90c4",fontSize:".72rem",padding:".1rem .4rem",borderRadius:"1px",marginLeft:".4rem"}}>fascia {FASCE_IMMOBILE.find(fc=>(parseFloat(f.base)||0)<=fc.max)?.label||""}</span> : ""} sul prezzo finale.<br/>
            {royaltyEst && <>Stima sulla base d'asta: <strong>€ {royaltyEst}</strong> → Riceverai: <strong>€ {(parseFloat(f.base) - parseFloat(royaltyEst)).toFixed(2)}</strong> (basato sul prezzo base).</>}
            {!royaltyEst && "Inserisci il prezzo base per vedere una stima."}
            <br/><span style={{fontSize:".74rem",color:"var(--muted)"}}>Nessuna commissione se l'asta non va a buon fine.</span>
          </div>
          <label className="chrow"><input type="checkbox" checked={f.comm} onChange={e=>upd("comm",e.target.checked)}/><span>✅ Confermo che la commissione del <strong>{getRoyalty(f.cat, f.base)}%</strong> {f.cat==="Immobili" ? "(tariffa immobili)" : "(beni mobili)"} è a carico dell'acquirente. <strong>Io venditore non pago commissioni.</strong></span></label>
          <label className="chrow"><input type="checkbox" checked={f.terms} onChange={e=>upd("terms",e.target.checked)}/><span>✅ Ho letto e accetto i <strong style={{color:"var(--amber)"}}>Termini e Condizioni</strong> di Battilo.</span></label>

          {/* ─── COMPRALO SUBITO ─── */}
          <div style={{marginTop:"1.3rem",borderTop:"1px solid var(--border)",paddingTop:"1.2rem"}}>
            <label className="lottoggle" style={{marginBottom:".7rem"}}>
              <input type="checkbox" checked={f.buyNow} onChange={e=>upd("buyNow",e.target.checked)}/>
              <div>
                <div className="lotlbl">⚡ Abilita "Compralo Subito"</div>
                <div className="lotsub">Un acquirente potrà concludere la vendita immediatamente al prezzo da te fissato, senza attendere la fine dell'asta.</div>
              </div>
            </label>
            {f.buyNow && (
              <div className="fg">
                <label className="fl">💰 Prezzo "Compralo Subito" (€) *</label>
                <input className="fi" type="number" placeholder="Es. 350"
                  style={{borderColor:"rgba(45,106,79,.4)",background:"rgba(45,106,79,.04)",fontFamily:"'Cormorant Garamond',serif",fontSize:"1.1rem"}}
                  value={f.buyNowPrice} onChange={e=>upd("buyNowPrice",e.target.value)}/>
                <span style={{fontSize:".7rem",color:"var(--muted)",marginTop:".2rem"}}>
                  Il prezzo "Compralo Subito" dovrebbe essere ≥ del prezzo di riserva. Una volta usato da un acquirente, l'asta si chiude immediatamente.
                </span>
              </div>
            )}
          </div>

          {/* ─── METODI DI PAGAMENTO ─── */}
          <div style={{marginTop:"1.2rem",borderTop:"1px solid var(--border)",paddingTop:"1.2rem"}}>
            <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"var(--muted)",marginBottom:".85rem"}}>💳 Metodi di pagamento accettati</div>
            <label className="chrow">
              <input type="checkbox" checked={f.payBonificoEnabled} onChange={e=>upd("payBonificoEnabled",e.target.checked)}/>
              <span>🏦 <strong>Bonifico bancario</strong> — L'acquirente riceverà le tue coordinate IBAN dopo l'aggiudicazione</span>
            </label>
            {f.payBonificoEnabled && (
              <div className="frow" style={{marginLeft:"1.5rem",marginBottom:".8rem"}}>
                <div className="fg">
                  <label className="fl">IBAN</label>
                  <input className="fi" placeholder="IT60 X054 2811 1010 0000 0123 456" value={f.ibanVend} onChange={e=>upd("ibanVend",e.target.value)}/>
                </div>
                <div className="fg">
                  <label className="fl">Intestatario conto</label>
                  <input className="fi" placeholder="Nome Cognome" value={f.intestatario} onChange={e=>upd("intestatario",e.target.value)}/>
                </div>
              </div>
            )}
            <label className="chrow">
              <input type="checkbox" checked={f.payCardEnabled} onChange={e=>upd("payCardEnabled",e.target.checked)}/>
              <span>💳 <strong>Carta di credito / debito</strong> — Pagamento sicuro tramite circuito Battilo (Visa, Mastercard, Amex)</span>
            </label>
            <label className="chrow" style={{marginBottom:"0"}}>
              <input type="checkbox" checked={f.payPaypalEnabled} onChange={e=>upd("payPaypalEnabled",e.target.checked)}/>
              <span>🅿 <strong>PayPal</strong> — L'acquirente potrà pagare con il proprio conto PayPal</span>
            </label>
          </div>
        </div>}

        {step===3 && <div className="sbody">
          <div className="stitle">Anteprima</div>
          <p className="ssub">Controlla tutto prima di pubblicare. Il tuo annuncio sarà revisionato dal team Battilo entro 24h.</p>
          <div style={{border:"1px solid var(--border)",borderRadius:"3px",overflow:"hidden",maxWidth:"290px",margin:"0 auto 1.4rem",boxShadow:"0 6px 24px rgba(28,26,23,.08)"}}>
            {f.photos[0]?<img src={f.photos[0]} alt="" style={{width:"100%",height:"170px",objectFit:"cover"}}/>:<div style={{height:"170px",background:"var(--amber-p)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:"2rem",opacity:.3}}>📷</div>}
            <div style={{padding:".9rem"}}>
              <div style={{fontSize:".62rem",letterSpacing:".1em",textTransform:"uppercase",color:"var(--amber)",marginBottom:".28rem"}}>{f.cat}</div>
              <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.12rem",marginBottom:".5rem"}}>{f.title||"Titolo oggetto"}</div>
              <div style={{display:"flex",justifyContent:"space-between",alignItems:"center"}}>
                <div><div style={{fontSize:".58rem",color:"var(--muted)"}}>Prezzo base</div><div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.3rem",fontWeight:600}}>€ {f.base||"—"}</div></div>
                <span style={{fontSize:".62rem",padding:".12rem .46rem",background:"rgba(200,133,42,.1)",color:"var(--amber)",borderRadius:"1px"}}>🔒 Riserva</span>
              </div>
            </div>
          </div>
          <div style={{background:"var(--cream)",border:"1px solid var(--border)",borderRadius:"2px",padding:".9rem",fontSize:".78rem",lineHeight:1.85}}>
            <div><strong>Venditore:</strong> {user?.name||"Tu"} <span style={{color:"var(--green)",marginLeft:".4rem",fontSize:".7rem"}}>✓ Verificato</span></div>
            <div><strong>Categoria:</strong> {f.cat} · Condizioni: {f.cond}</div>
            <div><strong>Durata:</strong> {f.start||"—"} → {f.end||"—"}</div>
            <div><strong>Prezzo base:</strong> € {f.base||"—"} &nbsp;·&nbsp; <strong>Riserva:</strong> <span style={{color:"var(--amber)"}}>🔒 privata</span></div>
            {f.photoService!=="self" && (
              <div style={{marginBottom:".3rem",padding:".5rem .7rem",background:"rgba(200,133,42,.06)",border:"1px solid rgba(200,133,42,.15)",borderRadius:"2px",fontSize:".75rem"}}>
                📸 <strong>Servizio Battilo richiesto:</strong> {f.photoService==="foto_imm"?"Foto immobile professionale":f.photoService==="tour"?"Virtual Tour 3D Matterport":"Bundle foto + virtual tour"} — <strong style={{color:"var(--amber)"}}>€ {f.photoService==="foto_imm"?FOTO_IMMOBILE_PRICE:f.photoService==="tour"?VIRTUAL_TOUR_PRICE:FOTO_BUNDLE_PRICE}</strong>
              </div>
            )}
            <div><strong>Commissione acquirente:</strong> <span style={{color:"var(--green)"}}>{getRoyalty(f.cat, f.base)}% {f.cat==="Immobili" ? "(tariffa immobili — ridotta)" : "(beni mobili)"}</span></div>
            {f.buyNow && <div><strong>⚡ Compralo Subito:</strong> <span style={{color:"var(--green)",fontWeight:600}}>€ {f.buyNowPrice}</span></div>}
            <div><strong>Regime fiscale:</strong> {f.regimeFiscale==="azienda" ? "🏢 Azienda/professionista" : "👤 Privato"}{f.regimeFiscale==="azienda" && f.cat!=="Immobili" ? (f.ivaEsposta ? " · 💶 IVA esposta inclusa" : " · IVA non esposta") : ""}{f.cat==="Immobili" ? ` · ${f.impostaImmobile==="iva" ? "🏢 Soggetto IVA" : "📋 Imposta di registro"}` : ""}</div>
            <div><strong>Pagamenti:</strong> {[f.payBonificoEnabled&&"Bonifico",f.payCardEnabled&&"Carta",f.payPaypalEnabled&&"PayPal"].filter(Boolean).join(" · ")||"Nessuno selezionato"}</div>
            {f.lot && <div><strong>Lotto:</strong> {f.lotName||f.lotEx||"—"}</div>}
            <div style={{marginTop:".5rem",color:"var(--muted)",fontSize:".74rem"}}>L'annuncio sarà revisionato entro 24h prima di essere visibile al pubblico.</div>
          </div>
        </div>}

        <div className="sacts">
          <span className="sprog">Step <strong>{step+1}</strong> di {SELL_STEPS.length}</span>
          <div style={{display:"flex",gap:".65rem"}}>
            {step>0&&<button className="sback" onClick={()=>setStep(s=>s-1)}>← Indietro</button>}
            <button className="snext"
              style={{opacity:canNext()?1:.38,cursor:canNext()?"pointer":"not-allowed"}}
              onClick={()=>{if(canNext())setStep(s=>s+1);}}>
              {step===SELL_STEPS.length-1?"🚀 Pubblica asta":"Avanti →"}
            </button>
          </div>
        </div>
      </div>
    </div>
  );
}

/* ─── ADMIN ─── */
function AdminPanel({ onBack, registeredUsers: propUsers, setRegisteredUsers }) {
  const [tab, setTab] = useState("items");
  const [royMobile, setRoyMobile] = useState(ROYALTY_MOBILE);
  const [fasce, setFasce] = useState(FASCE_IMMOBILE.map(f=>({...f})));
  const [openSections, setOpenSections] = useState({});
  const toggleSection = (key) => setOpenSections(p=>({...p,[key]:!p[key]}));
  const [docViewer, setDocViewer] = useState(null); // {dataUrl, mime, fileName}

  const openDoc = (dataUrl, mime, fileName) => {
    if(!dataUrl) return;
    setDocViewer({dataUrl, mime, fileName});
  };
  const downloadDoc = (dataUrl, fileName) => {
    if(!dataUrl) return;
    try {
      // Convert base64 dataUrl to Blob then download — works in sandboxed iframes
      const arr = dataUrl.split(',');
      const mimeMatch = arr[0].match(/:(.*?);/);
      const mime = mimeMatch ? mimeMatch[1] : 'application/octet-stream';
      const bstr = atob(arr[1]);
      const u8arr = new Uint8Array(bstr.length);
      for(let i=0;i<bstr.length;i++) u8arr[i]=bstr.charCodeAt(i);
      const blob = new Blob([u8arr], {type: mime});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url; a.download = fileName; a.click();
      setTimeout(()=>URL.revokeObjectURL(url), 1000);
    } catch(e) { alert('Download non disponibile in questo ambiente. Usa il visualizzatore.'); }
  };
  const updFascia = (i,val) => setFasce(prev => prev.map((f,j)=>j===i?{...f,pct:parseFloat(val)||f.pct}:f));
  const [userSearch, setUserSearch] = useState("");
  const [userFilter, setUserFilter] = useState("tutti"); // tutti | acquirenti | venditori
  const [selectedUser, setSelectedUser] = useState(null);
  const [resetEmailSent, setResetEmailSent] = useState(false);

  const MOCK_USERS = propUsers || [];

  const filteredUsers = MOCK_USERS.filter(u => {
    const matchType = userFilter==="tutti" || (userFilter==="acquirenti"&&u.type==="acquirente") || (userFilter==="venditori"&&u.type==="venditore");
    const matchSearch = u.name.toLowerCase().includes(userSearch.toLowerCase()) || u.email.toLowerCase().includes(userSearch.toLowerCase()) || u.id.toLowerCase().includes(userSearch.toLowerCase());
    return matchType && matchSearch;
  });


  const [cauPct, setCauPct] = useState(CAUZIONE_PCT);
  const [cauFixed, setCauFixed] = useState(CAUZIONE_FIXED);
  // Coordinate bancarie piattaforma (cauzioni + commissioni)
  const [banca, setBanca] = useState({
    intestatario: "Battilo S.r.l.",
    iban: "IT60 X054 2811 1010 0000 0123 456",
    bic: "BPMOIT22XXX",
    banca: "Banco BPM",
    causaleAsta: "BATTILO-{ID}-CAUZIONE",
    causaleComm: "BATTILO-{ID}-COMMISSIONE",
  });
  const updBanca = (k,v) => setBanca(p=>({...p,[k]:v}));
  return (
    <div className="adm">
      {/* ── DOC VIEWER MODAL ── */}
      {docViewer && (
        <div style={{position:"fixed",inset:0,zIndex:500,background:"rgba(0,0,0,.88)",display:"flex",flexDirection:"column",alignItems:"center",justifyContent:"center",padding:"1rem"}}
          onClick={()=>setDocViewer(null)}>
          <div style={{width:"100%",maxWidth:"820px",display:"flex",flexDirection:"column",gap:".6rem"}} onClick={e=>e.stopPropagation()}>
            <div style={{display:"flex",alignItems:"center",justifyContent:"space-between",padding:".5rem .8rem",background:"rgba(253,250,246,.06)",borderRadius:"3px 3px 0 0"}}>
              <span style={{fontFamily:"monospace",fontSize:".8rem",color:"rgba(253,250,246,.7)"}}>{docViewer.fileName}</span>
              <div style={{display:"flex",gap:".5rem"}}>
                <button className="bag" style={{fontSize:".72rem"}} onClick={()=>downloadDoc(docViewer.dataUrl,docViewer.fileName)}>⬇ Scarica</button>
                <button className="bag" style={{fontSize:".72rem",color:"#e07070",borderColor:"rgba(180,40,40,.3)"}} onClick={()=>setDocViewer(null)}>✕ Chiudi</button>
              </div>
            </div>
            <div style={{background:"#fff",borderRadius:"0 0 3px 3px",overflow:"hidden",maxHeight:"80vh",display:"flex",alignItems:"center",justifyContent:"center"}}>
              {docViewer.mime && docViewer.mime.startsWith("image/")
                ? <img src={docViewer.dataUrl} alt={docViewer.fileName} style={{maxWidth:"100%",maxHeight:"80vh",objectFit:"contain",display:"block"}}/>
                : docViewer.mime === "application/pdf"
                  ? <iframe src={docViewer.dataUrl} title={docViewer.fileName} style={{width:"100%",height:"75vh",border:"none"}}/>
                  : <div style={{padding:"2rem",color:"#666",textAlign:"center"}}>Anteprima non disponibile per questo tipo di file.<br/>Usa il pulsante Scarica.</div>
              }
            </div>
          </div>
        </div>
      )}
      <div className="admnav">
        <Logo size={32} textSize="1.1rem" dark/>
        <span style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1rem",fontWeight:300,color:"rgba(253,250,246,.38)",marginLeft:".5rem"}}>/ Pannello Admin</span>
        <button className="bag" style={{marginLeft:"auto"}} onClick={onBack}>← Sito pubblico</button>
      </div>
      <div className="admcont">
        <div className="admstats">
          {[["Aste Attive","24"],["In Scadenza","6"],["Approvazione","3"],["Offerte Oggi","142"]].map(([l,n])=>(
            <div key={l} className="asc"><div className="ascl">{l}</div><div className="ascn">{n}</div></div>
          ))}
        </div>
        <div className="tabs">
          {[["items","Oggetti & Aste"],["users","Anagrafica Iscritti"],["sellers","Venditori"],["royalties","Royalties"],["cauzione","Cauzione"],["settings","Impostazioni"]].map(([k,v])=>(
            <div key={k} className={`tab ${tab===k?"on":""}`} onClick={()=>setTab(k)}>{v}</div>
          ))}
        </div>

        {tab==="items" && <>
          <div className="admtitle">Oggetti in moderazione</div>
          {["Bicicletta vintage Bianchi 1974","Collezione francobolli 1940-1960","Orologio Omega Seamaster"].map((t,i)=>(
            <div key={i} className="modit">
              <div className="modinfo"><div className="modname">{t}</div><div className="modseller">Inviato da: venditore_0{i+1} · 2 ore fa</div></div>
              <div style={{display:"flex",gap:".5rem"}}>
                <button className="bag" style={{color:"#e05c4e",borderColor:"rgba(192,57,43,.25)"}}>✕ Rifiuta</button>
                <button className="baf">✓ Approva</button>
              </div>
            </div>
          ))}
        </>}

        {/* ══ ANAGRAFICA ISCRITTI ══ */}
        {tab==="users" && <>
          {!selectedUser ? (
            <>
              <div className="admtitle">📋 Anagrafica Iscritti</div>
              {/* Filtri + ricerca */}
              <div style={{display:"flex",gap:".8rem",flexWrap:"wrap",marginBottom:"1.2rem",alignItems:"center"}}>
                <input
                  className="afi" style={{flex:1,minWidth:"180px",background:"rgba(253,250,246,.06)"}}
                  placeholder="🔍 Cerca per nome, email o ID..."
                  value={userSearch} onChange={e=>setUserSearch(e.target.value)}/>
                <div style={{display:"flex",gap:".4rem"}}>
                  {[["tutti","Tutti"],["acquirenti","👤 Acquirenti"],["venditori","🏪 Venditori"]].map(([v,l])=>(
                    <button key={v}
                      style={{padding:".35rem .85rem",fontSize:".72rem",border:`1px solid ${userFilter===v?"var(--amber)":"rgba(253,250,246,.15)"}`,background:userFilter===v?"rgba(200,133,42,.15)":"transparent",color:"var(--warm)",borderRadius:"2px",cursor:"pointer",letterSpacing:".05em"}}
                      onClick={()=>setUserFilter(v)}>{l}</button>
                  ))}
                </div>
                <span style={{fontSize:".72rem",color:"rgba(253,250,246,.35)",marginLeft:"auto"}}>{filteredUsers.length} iscritti</span>
              </div>
              {/* Tabella iscritti */}
              <div style={{overflowX:"auto"}}>
                <table style={{width:"100%",borderCollapse:"collapse",fontSize:".78rem"}}>
                  <thead>
                    <tr style={{borderBottom:"1px solid rgba(253,250,246,.12)"}}>
                      {["ID","Nome","Email","Tipo","Stato","Registrazione","Ultimo accesso","Azioni"].map(h=>(
                        <th key={h} style={{padding:".55rem .7rem",textAlign:"left",fontSize:".62rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.35)",fontWeight:400}}>{h}</th>
                      ))}
                    </tr>
                  </thead>
                  <tbody>
                    {filteredUsers.map((u,i)=>(
                      <tr key={u.id} style={{borderBottom:"1px solid rgba(253,250,246,.06)",background:i%2===0?"transparent":"rgba(253,250,246,.02)"}}>
                        <td style={{padding:".6rem .7rem",color:"rgba(253,250,246,.4)",fontFamily:"monospace",fontSize:".7rem"}}>{u.id}</td>
                        <td style={{padding:".6rem .7rem"}}>
                          <div style={{display:"flex",alignItems:"center",gap:".5rem"}}>
                            <div style={{width:"28px",height:"28px",borderRadius:"50%",background:"var(--amber)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:".72rem",fontWeight:700,color:"var(--char)",flexShrink:0}}>{u.name[0]}</div>
                            <span style={{color:"var(--warm)",fontWeight:500}}>{u.name}</span>{u.status==="pending"&&<span style={{fontSize:".58rem",padding:".1rem .35rem",background:"rgba(200,133,42,.18)",color:"var(--amber)",borderRadius:"1px",letterSpacing:".05em"}}>NUOVO</span>}
                            {u.verified && <span style={{fontSize:".6rem",color:"var(--green)"}}>✓</span>}
                          </div>
                        </td>
                        <td style={{padding:".6rem .7rem",color:"rgba(253,250,246,.55)"}}>{u.email}</td>
                        <td style={{padding:".6rem .7rem"}}>
                          <span style={{fontSize:".65rem",padding:".12rem .45rem",borderRadius:"1px",background:u.type==="venditore"?"rgba(200,133,42,.15)":"rgba(45,106,79,.12)",color:u.type==="venditore"?"var(--amber-l)":"#7ecba0",letterSpacing:".06em",textTransform:"uppercase"}}>
                            {u.type==="venditore"?"🏪 Venditore":"👤 Acquirente"}{u.entityType==="societa"?" 🏢":""}
                          </span>
                        </td>
                        <td style={{padding:".6rem .7rem"}}>
                          <span style={{fontSize:".65rem",padding:".12rem .45rem",borderRadius:"1px",
                            background:u.status==="attivo"?"rgba(45,106,79,.15)":u.status==="sospeso"?"rgba(200,133,42,.15)":"rgba(180,40,40,.15)",
                            color:u.status==="attivo"?"#7ecba0":u.status==="sospeso"?"var(--amber-l)":"#e07070",
                            textTransform:"uppercase",letterSpacing:".06em"}}>
                            {u.status}
                          </span>
                        </td>
                        <td style={{padding:".6rem .7rem",color:"rgba(253,250,246,.4)",fontSize:".72rem"}}>{u.regDate}</td>
                        <td style={{padding:".6rem .7rem",color:"rgba(253,250,246,.4)",fontSize:".72rem"}}>{u.lastLogin}</td>
                        <td style={{padding:".6rem .7rem"}}>
                          <div style={{display:"flex",gap:".35rem"}}>
                            <button className="bag" style={{fontSize:".68rem",padding:".2rem .6rem"}} onClick={()=>{setSelectedUser(u);setResetEmailSent(false);}}>👁 Scheda</button>
                          </div>
                        </td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            </>
          ) : (
            /* ── SCHEDA ISCRITTO ── */
            <div>
              <button className="bag" style={{marginBottom:"1.2rem",fontSize:".78rem"}} onClick={()=>setSelectedUser(null)}>← Torna all'elenco</button>
              <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:"1.2rem",flexWrap:"wrap"}}>
                {/* Dati anagrafici */}
                <div style={{background:"rgba(253,250,246,.04)",border:"1px solid rgba(253,250,246,.1)",borderRadius:"3px",padding:"1.2rem",gridColumn:"1/-1"}}>
                  <div style={{display:"flex",alignItems:"center",gap:"1rem",marginBottom:"1rem",flexWrap:"wrap"}}>
                    <div style={{width:"52px",height:"52px",borderRadius:"50%",background:"var(--amber)",display:"flex",alignItems:"center",justifyContent:"center",fontSize:"1.4rem",fontWeight:700,color:"var(--char)",flexShrink:0}}>{selectedUser.name[0]}</div>
                    <div>
                      <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.4rem",color:"var(--warm)"}}>{selectedUser.name}</div>
                      <div style={{fontSize:".75rem",color:"rgba(253,250,246,.45)"}}>{selectedUser.id} · Iscritto dal {selectedUser.regDate} · Ultimo accesso: {selectedUser.lastLogin}</div>
                    </div>
                    <div style={{marginLeft:"auto",display:"flex",gap:".5rem",flexWrap:"wrap"}}>
                      <span style={{fontSize:".68rem",padding:".2rem .6rem",borderRadius:"1px",
                        background:selectedUser.type==="venditore"?"rgba(200,133,42,.15)":"rgba(45,106,79,.12)",
                        color:selectedUser.type==="venditore"?"var(--amber-l)":"#7ecba0",textTransform:"uppercase",letterSpacing:".06em"}}>
                        {selectedUser.type==="venditore"?"🏪 Venditore":"👤 Acquirente"}
                      </span>
                      <span style={{fontSize:".68rem",padding:".2rem .6rem",borderRadius:"1px",
                        background:selectedUser.status==="attivo"?"rgba(45,106,79,.15)":selectedUser.status==="sospeso"?"rgba(200,133,42,.15)":"rgba(180,40,40,.15)",
                        color:selectedUser.status==="attivo"?"#7ecba0":selectedUser.status==="sospeso"?"var(--amber-l)":"#e07070",
                        textTransform:"uppercase",letterSpacing:".06em"}}>
                        {selectedUser.status}
                      </span>
                      {selectedUser.verified && <span style={{fontSize:".68rem",padding:".2rem .6rem",borderRadius:"1px",background:"rgba(45,106,79,.15)",color:"#7ecba0"}}>✓ Verificato</span>}
                    </div>
                  </div>
                  <div style={{display:"grid",gridTemplateColumns:"repeat(auto-fill,minmax(200px,1fr))",gap:".7rem",fontSize:".78rem"}}>
                    {[
                      ["Email",selectedUser.email],
                      ["Telefono",selectedUser.phone||"—"],
                      ["Codice fiscale",selectedUser.taxCode||"—"],
                      ["Aste create",selectedUser.aste],
                      ["Offerte effettuate",selectedUser.offerte],
                      ["Cauzioni attive",selectedUser.cauzioni],
                      ["Indirizzo",selectedUser.indirizzo?(selectedUser.indirizzo+(selectedUser.cap?" — "+selectedUser.cap:"")+(selectedUser.citta?" "+selectedUser.citta:"")+(selectedUser.provincia?" ("+selectedUser.provincia+")":"")):null],
                      ["SDI / Codice destinatario",selectedUser.sdi||"0000000"],
                      ["PEC",selectedUser.pec||null],
                    ].map(([k,v])=>(
                      <div key={k} style={{background:"rgba(253,250,246,.04)",borderRadius:"2px",padding:".6rem .8rem"}}>
                        <div style={{fontSize:".62rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.3)",marginBottom:".2rem"}}>{k}</div>
                        <div style={{color:"var(--warm)",fontFamily:k==="Codice fiscale"||k==="Email"?"monospace":"inherit",fontSize:k==="Codice fiscale"?"0.72rem":"inherit"}}>{v}</div>
                      </div>
                    ))}
                  </div>
                  {selectedUser.entityType==="societa" && selectedUser.companyName && (
                    <div style={{marginTop:".9rem",padding:".85rem 1rem",background:"rgba(26,77,124,.06)",border:"1px solid rgba(26,77,124,.2)",borderRadius:"2px",fontSize:".75rem"}}>
                      <div style={{fontSize:".62rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(100,160,210,.6)",marginBottom:".7rem"}}>🏢 Dati societari</div>
                      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:".5rem"}}>
                        {[["Ragione sociale",selectedUser.companyName],["P.IVA",selectedUser.piva],["Legale rappresentante",selectedUser.legalRepName],["Ruolo",selectedUser.legalRepRole]].filter(([,v])=>v).map(([k,v])=>(
                          <div key={k}><div style={{fontSize:".6rem",color:"rgba(253,250,246,.3)",textTransform:"uppercase",letterSpacing:".06em"}}>{k}</div><div style={{color:"var(--warm)",fontFamily:k==="P.IVA"?"monospace":"inherit"}}>{v}</div></div>
                        ))}
                      </div>
                      {/* Visura camerale */}
                      {selectedUser.visuraFileName && (
                        <div style={{marginTop:".8rem",paddingTop:".7rem",borderTop:"1px solid rgba(26,77,124,.18)",display:"flex",alignItems:"center",gap:".7rem",flexWrap:"wrap"}}>
                          <span style={{fontSize:"1rem"}}>📑</span>
                          <span style={{fontFamily:"monospace",color:"var(--warm)",fontSize:".72rem",flex:1}}>{selectedUser.visuraFileName}</span>
                          <button className="bag" style={{fontSize:".68rem",padding:".18rem .6rem"}} onClick={()=>downloadDoc(selectedUser.visuraDataUrl, selectedUser.visuraFileName)}>⬇ Scarica visura</button>
                          {selectedUser.visuraDataUrl && (
                            <button className="bag" style={{fontSize:".68rem",padding:".18rem .6rem"}} onClick={()=>openDoc(selectedUser.visuraDataUrl, selectedUser.visuraMime, selectedUser.visuraFileName)}>🔍 Visualizza</button>
                          )}
                        </div>
                      )}
                    </div>
                  )}
                  {selectedUser.type==="venditore" && selectedUser.iban && (
                    <div style={{marginTop:".9rem",padding:".7rem .9rem",background:"rgba(200,133,42,.05)",border:"1px solid rgba(200,133,42,.15)",borderRadius:"2px",fontSize:".75rem"}}>
                      <div style={{fontSize:".62rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.3)",marginBottom:".25rem"}}>🏦 IBAN venditore (saldo prezzo)</div>
                      <span style={{fontFamily:"monospace",color:"var(--amber-l)",letterSpacing:".05em"}}>{selectedUser.iban}</span>
                    </div>
                  )}
                  {selectedUser.type==="venditore" && (
                    <div style={{marginTop:".9rem",padding:".85rem 1rem",background:"rgba(253,250,246,.04)",border:"1px solid rgba(253,250,246,.1)",borderRadius:"2px",fontSize:".75rem"}}>
                      <div style={{fontSize:".62rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.3)",marginBottom:".7rem"}}>📄 Documento d'identità allegato</div>
                      {selectedUser.docFileName && selectedUser.docDataUrl ? (() => {
                        const isPdf = selectedUser.docMime==="application/pdf";
                        const isImg = selectedUser.docMime && selectedUser.docMime.startsWith("image/");
                        const handleDownload = () => downloadDoc(selectedUser.docDataUrl, selectedUser.docFileName);
                        return (
                          <div>
                            <div style={{display:"flex",alignItems:"center",gap:".8rem",marginBottom:".7rem",flexWrap:"wrap"}}>
                              <span style={{fontFamily:"monospace",color:"var(--warm)",fontSize:".73rem",flex:1}}>{selectedUser.docFileName}</span>
                              <span style={{color:"var(--green)",fontSize:".72rem",fontWeight:600}}>✓ acquisito</span>
                              <button className="bag" style={{fontSize:".68rem",padding:".2rem .7rem"}}
                                onClick={handleDownload}>⬇ Scarica</button>
                              <button className="bag" style={{fontSize:".68rem",padding:".2rem .7rem"}}
                                onClick={()=>openDoc(selectedUser.docDataUrl, selectedUser.docMime, selectedUser.docFileName)}>🔍 Visualizza</button>
                            </div>
                            {isImg && (
                              <div style={{marginTop:".5rem",padding:".5rem",background:"rgba(255,255,255,.05)",borderRadius:"2px",textAlign:"center"}}>
                                <img src={selectedUser.docDataUrl} alt="documento identità"
                                  style={{maxWidth:"100%",maxHeight:"220px",objectFit:"contain",borderRadius:"2px",border:"1px solid rgba(253,250,246,.15)"}}/>
                              </div>
                            )}
                            {isPdf && (
                              <div style={{marginTop:".5rem",padding:".6rem .8rem",background:"rgba(26,77,124,.08)",border:"1px solid rgba(26,77,124,.18)",borderRadius:"2px",fontSize:".72rem",color:"#6aabdf"}}>
                                📑 PDF allegato — usa "Visualizza" per aprirlo o "Scarica" per salvarlo.
                              </div>
                            )}
                          </div>
                        );
                      })() : (
                        <span style={{color:"rgba(253,250,246,.35)",fontSize:".73rem",fontStyle:"italic"}}>
                          {selectedUser.docFileName ? `${selectedUser.docFileName} — anteprima non disponibile (registrazione precedente)` : "Nessun documento caricato"}
                        </span>
                      )}
                    </div>
                  )}
                </div>
                {/* Azioni admin */}
                <div style={{background:"rgba(253,250,246,.04)",border:"1px solid rgba(253,250,246,.1)",borderRadius:"3px",padding:"1.2rem"}}>
                  <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.32)",marginBottom:".9rem"}}>⚙️ Azioni account</div>
                  <div style={{display:"flex",flexDirection:"column",gap:".55rem"}}>
                    {selectedUser.status==="attivo"
                      ? <button className="bag" onClick={()=>{ setRegisteredUsers(p=>p.map(u=>u.id===selectedUser.id?{...u,status:'sospeso'}:u)); setSelectedUser(p=>({...p,status:'sospeso'})); }}>⏸ Sospendi account</button>
                      : <button className="baf" onClick={()=>{ setRegisteredUsers(p=>p.map(u=>u.id===selectedUser.id?{...u,status:'attivo'}:u)); setSelectedUser(p=>({...p,status:'attivo'})); }}>▶ Riattiva account</button>
                    }
                    {selectedUser.status!=="bloccato"
                      ? <button style={{background:"rgba(180,40,40,.2)",color:"#e07070",border:"1px solid rgba(180,40,40,.3)",padding:".45rem .9rem",borderRadius:"2px",cursor:"pointer",fontSize:".78rem"}} onClick={()=>{ setRegisteredUsers(p=>p.map(u=>u.id===selectedUser.id?{...u,status:'bloccato'}:u)); setSelectedUser(p=>({...p,status:'bloccato'})); }}>🚫 Blocca account</button>
                      : <button className="baf" onClick={()=>{ setRegisteredUsers(p=>p.map(u=>u.id===selectedUser.id?{...u,status:'attivo'}:u)); setSelectedUser(p=>({...p,status:'attivo'})); }}>🔓 Sblocca account</button>
                    }
                    {selectedUser.type==="acquirente" && (
                      <button className="bag" onClick={()=>{ setRegisteredUsers(p=>p.map(u=>u.id===selectedUser.id?{...u,type:'venditore',status:'pending'}:u)); setSelectedUser(p=>({...p,type:'venditore',status:'pending'})); }}>🏪 Promuovi a venditore</button>
                    )}
                  </div>
                </div>
                {/* Reset password */}
                <div style={{background:"rgba(253,250,246,.04)",border:"1px solid rgba(253,250,246,.1)",borderRadius:"3px",padding:"1.2rem"}}>
                  <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.32)",marginBottom:".9rem"}}>🔑 Recupero password</div>
                  {!resetEmailSent ? (
                    <>
                      <p style={{fontSize:".78rem",color:"rgba(253,250,246,.45)",lineHeight:1.7,marginBottom:".9rem"}}>
                        Invia all'utente un link sicuro per reimpostare la password. Il link scade dopo 24 ore.
                      </p>
                      <div style={{background:"rgba(253,250,246,.04)",borderRadius:"2px",padding:".6rem .9rem",fontSize:".72rem",fontFamily:"monospace",color:"rgba(253,250,246,.5)",marginBottom:".85rem",letterSpacing:".02em"}}>
                        → {selectedUser.email}
                      </div>
                      <button className="baf" onClick={()=>setResetEmailSent(true)}>
                        📧 Invia link reset password
                      </button>
                    </>
                  ) : (
                    <div style={{padding:".85rem 1rem",background:"rgba(45,106,79,.1)",border:"1px solid rgba(45,106,79,.25)",borderRadius:"2px",fontSize:".78rem",color:"#7ecba0",lineHeight:1.75}}>
                      ✅ <strong>Email inviata</strong> a {selectedUser.email}<br/>
                      <span style={{color:"rgba(253,250,246,.4)",fontSize:".72rem"}}>Link valido 24 ore. L'utente riceverà istruzioni per reimpostare la password.</span>
                      <br/><button className="bag" style={{marginTop:".6rem",fontSize:".72rem"}} onClick={()=>setResetEmailSent(false)}>Invia di nuovo</button>
                    </div>
                  )}
                </div>
              </div>
            </div>
          )}
        </>}

        {tab==="sellers" && <>
          <div className="admtitle">Gestione venditori registrati</div>
          {[
            {name:"Marco Conti",email:"m.conti@mail.it",status:"ok",sold:7,pending:"€ 145"},
            {name:"Francesca Bianchi",email:"f.bianchi@mail.it",status:"pending",sold:0,pending:"—"},
            {name:"Luca Verdi",email:"l.verdi@mail.it",status:"ok",sold:3,pending:"€ 58"},
            {name:"Giorgio Mori",email:"g.mori@mail.it",status:"rejected",sold:0,pending:"—"},
          ].map((s,i)=>(
            <div key={i} className="modit">
              <div className="modinfo">
                <div className="modname" style={{display:"flex",alignItems:"center",gap:".6rem"}}>
                  {s.name}
                  <span className={`seller-badge ${s.status==="ok"?"sb-ok":s.status==="pending"?"sb-pending":"sb-rejected"}`}>
                    {s.status==="ok"?"✓ Verificato":s.status==="pending"?"⏳ In attesa":"✕ Rifiutato"}
                  </span>
                </div>
                <div className="modseller">{s.email} · {s.sold} oggetti venduti · Royalty pendente: {s.pending}</div>
              </div>
              <div style={{display:"flex",gap:".5rem"}}>
                <button className="bag">👁 Vedi doc.</button>
                {s.status==="pending" && <button className="baf">✓ Approva</button>}
              </div>
            </div>
          ))}
        </>}

        {tab==="royalties" && <>
          <div className="admtitle">Gestione royalties — Mobili: <span style={{color:"var(--amber-l)"}}>{royMobile}%</span> · Immobili: <span style={{color:"#6aabdf"}}>per fascia</span></div>
          <div style={{background:"rgba(253,250,246,.04)",border:"1px solid rgba(253,250,246,.08)",borderRadius:"3px",padding:"1.2rem",marginBottom:"1.8rem"}}>
            <div style={{display:"flex",gap:"1.5rem",flexWrap:"wrap",marginBottom:"1rem"}}>
              <div>
                <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.32)",marginBottom:".5rem"}}>🪑 Beni mobili (%)</div>
                <div className="pct-row">
                  <input className="pct-input" type="number" min="1" max="30" value={royMobile} onChange={e=>setRoyMobile(e.target.value)}/>
                  <span style={{color:"rgba(253,250,246,.4)",fontSize:"1.2rem"}}>%</span>
                </div>
              </div>
              <div style={{flex:"1 1 100%"}}>
                <div style={{fontSize:".68rem",letterSpacing:".08em",textTransform:"uppercase",color:"rgba(253,250,246,.32)",marginBottom:".7rem"}}>🏠 Immobili — commissioni per fascia di prezzo</div>
                <div style={{display:"grid",gridTemplateColumns:"1fr auto",gap:".4rem .8rem",alignItems:"center"}}>
                  {fasce.map((f,i)=>(
                    <React.Fragment key={i}>
                      <span style={{fontSize:".76rem",color:"rgba(253,250,246,.55)"}}>{f.label}</span>
                      <div className="pct-row" style={{gap:".3rem"}}>
                        <input className="pct-input" type="number" min="0.5" max="10" step="0.5"
                          value={f.pct} onChange={e=>updFascia(i,e.target.value)}
                          style={{color:"#6aabdf",width:"60px"}}/>
                        <span style={{color:"rgba(253,250,246,.4)"}}>%</span>
                      </div>
                    </React.Fragment>
                  ))}
                </div>
              </div>
              <div style={{alignSelf:"flex-end",paddingBottom:".2rem"}}>
                <button className="baf">Salva tariffe</button>
              </div>
            </div>
            <p style={{fontSize:".74rem",color:"rgba(253,250,246,.3)"}}>Le tariffe si applicano alle nuove aste. Le aste in corso mantengono la commissione precedente.</p>
          </div>
          <div className="admtitle" style={{fontSize:"1.1rem"}}>Royalties da incassare</div>
          {[
            {seller:"Marco Conti",item:"Olio su tela",sale:340,pct:ROYALTY_MOBILE,cat:"mobile",status:"pending"},
            {seller:"Francesca Bianchi",item:"Libreria Noce",sale:580,pct:ROYALTY_MOBILE,cat:"mobile",status:"paid"},
            {seller:"Luca Verdi",item:"Vinili Jazz x40",sale:290,pct:ROYALTY_MOBILE,cat:"mobile",status:"pending"},
            {seller:"G. Martinelli",item:"App. Milano Navigli",sale:185000,pct:getRoyaltyImmobile(185000),cat:"immobile",status:"pending"},
            {seller:"Luca Verdi",item:"Leica M6",sale:1240,pct:ROYALTY_MOBILE,cat:"mobile",status:"paid"},
          ].map((r,i)=>(
            <div key={i} className="roy-row">
              <div className="roy-info">
                <div style={{fontWeight:500,marginBottom:".18rem"}}>{r.item}</div>
                <div style={{fontSize:".72rem",color:"rgba(253,250,246,.35)"}}>{r.seller} · Venduto a € {r.sale.toLocaleString("it")}</div>
              </div>
              <div style={{display:"flex",alignItems:"center",gap:"1rem"}}>
                <div className="roy-amount">€ {(r.sale*r.pct/100).toFixed(2)}</div>
                <span className={`roy-status ${r.status==="paid"?"rs-paid":"rs-pending"}`}>{r.status==="paid"?"Incassata":"In attesa"}</span>
                {r.status==="pending" && <button className="baf" style={{padding:".3rem .75rem",fontSize:".68rem"}}>Incassa</button>}
              </div>
            </div>
          ))}
          <div style={{marginTop:"1.5rem",padding:"1rem",background:"rgba(253,250,246,.04)",borderRadius:"2px",fontSize:".82rem",color:"rgba(253,250,246,.5)"}}>
            Totale royalties incassate questo mese: <span style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.3rem",color:"var(--amber-l)",marginLeft:".4rem"}}>€ {(580*ROYALTY_MOBILE/100 + 1240*ROYALTY_MOBILE/100).toFixed(2)}</span>
          </div>
        </>}

        {tab==="settings" && <>
          <div className="admtitle">Impostazioni piattaforma</div>
          <p style={{fontSize:".78rem",color:"rgba(253,250,246,.4)",marginBottom:"1.2rem",lineHeight:1.6}}>Clicca su una sezione per espanderla e modificarne i valori.</p>

          {/* ── ACCORDION HELPER ── */}
          {[
            {
              key:"generale", icon:"⚙️", label:"Impostazioni generali",
              summary:"Nome piattaforma · Email supporto · Anti-sniping · Durata asta",
              content: (
                <>
                  <div className="afrow" style={{marginBottom:".9rem"}}>
                    <div className="afg"><label className="afl">Nome piattaforma</label><input className="afi" defaultValue="Battilo"/></div>
                    <div className="afg"><label className="afl">Email supporto</label><input className="afi" defaultValue="supporto@battilo.it"/></div>
                  </div>
                  <div className="afrow">
                    <div className="afg"><label className="afl">Anti-sniping (minuti)</label><input className="afi" type="number" defaultValue="2"/></div>
                    <div className="afg"><label className="afl">Giorni max durata asta</label><input className="afi" type="number" defaultValue="30"/></div>
                  </div>
                </>
              )
            },
            {
              key:"foto", icon:"📸", label:"Servizio Fotografico & Virtual Tour",
              summary:"Listino prezzi foto immobili · Virtual Tour Matterport · Bundle",
              content: (
                <>
                  <p style={{fontSize:".78rem",color:"rgba(253,250,246,.45)",lineHeight:1.75,marginBottom:"1rem"}}>
                    Definisci i prezzi per i servizi opzionali offerti ai venditori di immobili.
                  </p>
                  <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:".85rem",marginBottom:"1rem"}}>
                    {[
                      ["fotoImmPrice","🏠📸 Foto immobile professionale",FOTO_IMMOBILE_PRICE],
                      ["tourPrice","🔮 Virtual Tour 3D Matterport",VIRTUAL_TOUR_PRICE],
                      ["bundlePrice","✨ Bundle foto + Virtual Tour",FOTO_BUNDLE_PRICE],
                    ].map(([k,label,def])=>(
                      <div key={k} className="afg">
                        <label className="afl">{label}</label>
                        <div style={{display:"flex",alignItems:"center",gap:".5rem"}}>
                          <span style={{color:"rgba(253,250,246,.4)"}}>€</span>
                          <input className="afi" type="number" min="0" step="10" defaultValue={def} style={{flex:1}}/>
                        </div>
                      </div>
                    ))}
                  </div>
                  <label style={{display:"flex",alignItems:"center",gap:".5rem",cursor:"pointer",fontSize:".8rem",color:"var(--warm)"}}>
                    <input type="checkbox" defaultChecked={FOTO_SERVICE_ENABLED} style={{accentColor:"var(--amber)"}}/>
                    Abilita i servizi fotografici nella piattaforma
                  </label>
                </>
              )
            },
            {
              key:"banca", icon:"🏦", label:"Coordinate bancarie — Cauzioni & Commissioni",
              summary:`IBAN: ${banca.iban.slice(0,18)}… · BIC: ${banca.bic}`,
              content: (
                <>
                  <p style={{fontSize:".78rem",color:"rgba(253,250,246,.45)",lineHeight:1.75,marginBottom:"1rem"}}>
                    Cauzioni e commissioni accreditate su questo conto. Il saldo prezzo va direttamente al venditore.
                  </p>
                  <div className="afrow" style={{marginBottom:".8rem"}}>
                    <div className="afg"><label className="afl">Intestatario conto</label><input className="afi" value={banca.intestatario} onChange={e=>updBanca("intestatario",e.target.value)}/></div>
                    <div className="afg"><label className="afl">Banca</label><input className="afi" value={banca.banca} onChange={e=>updBanca("banca",e.target.value)}/></div>
                  </div>
                  <div className="afrow" style={{marginBottom:".8rem"}}>
                    <div className="afg" style={{flex:2}}><label className="afl">IBAN</label><input className="afi" value={banca.iban} onChange={e=>updBanca("iban",e.target.value)} style={{fontFamily:"monospace",letterSpacing:".05em"}}/></div>
                    <div className="afg"><label className="afl">BIC / SWIFT</label><input className="afi" value={banca.bic} onChange={e=>updBanca("bic",e.target.value)} style={{fontFamily:"monospace"}}/></div>
                  </div>
                  <div className="afrow">
                    <div className="afg"><label className="afl">Causale cauzione (usa {"{ID}"})</label><input className="afi" value={banca.causaleAsta} onChange={e=>updBanca("causaleAsta",e.target.value)}/></div>
                    <div className="afg"><label className="afl">Causale commissione (usa {"{ID}"})</label><input className="afi" value={banca.causaleComm} onChange={e=>updBanca("causaleComm",e.target.value)}/></div>
                  </div>
                </>
              )
            },
            {
              key:"flusso", icon:"⚙️", label:"Flusso di pagamento post-aggiudicazione",
              summary:"7 step: aggiudicazione → cauzione → commissione → saldo → consegna",
              content: (
                <>
                  <div style={{display:"grid",gridTemplateColumns:"auto 1fr",gap:".5rem 1rem",fontSize:".8rem",lineHeight:1.9,marginBottom:"1rem"}}>
                    {[
                      ["1","🔨 Asta aggiudicata — acquirente riceve notifica"],
                      ["2","🔐 Acquirente versa la CAUZIONE su conto Battilo"],
                      ["3","💳 Acquirente versa la COMMISSIONE D'ASTA su conto Battilo"],
                      ["4","✅ Battilo verifica i pagamenti — sblocca la fase successiva"],
                      ["5","🏦 Sistema invia coordinate bancarie del venditore all'acquirente"],
                      ["6","💶 Acquirente versa il saldo prezzo direttamente al venditore"],
                      ["7","📦 Venditore ricevuto il saldo → procede alla consegna"],
                    ].map(([n,t])=>(
                      <React.Fragment key={n}>
                        <div style={{width:"22px",height:"22px",background:"var(--amber)",borderRadius:"50%",display:"flex",alignItems:"center",justifyContent:"center",fontSize:".65rem",fontWeight:700,color:"var(--char)",flexShrink:0,marginTop:".15rem"}}>{n}</div>
                        <div style={{color:"rgba(253,250,246,.7)"}}>{t}</div>
                      </React.Fragment>
                    ))}
                  </div>
                  <div style={{padding:".75rem 1rem",background:"rgba(200,133,42,.08)",border:"1px solid rgba(200,133,42,.18)",borderRadius:"2px",fontSize:".75rem",color:"rgba(253,250,246,.5)",lineHeight:1.75}}>
                    ⚠️ <strong style={{color:"var(--amber-l)"}}>Blocco automatico:</strong> coordinate del venditore inviate solo dopo conferma commissione ricevuta.
                  </div>
                </>
              )
            }
          ].map(({key,icon,label,summary,content})=>(
            <div key={key} style={{marginBottom:".6rem",borderRadius:"3px",overflow:"hidden"}}>
              {/* Header */}
              <div style={{display:"flex",alignItems:"center",justifyContent:"space-between",padding:".85rem 1.1rem",cursor:"pointer",userSelect:"none",background:openSections[key]?"rgba(200,133,42,.1)":"rgba(253,250,246,.05)",border:`1px solid ${openSections[key]?"rgba(200,133,42,.3)":"rgba(253,250,246,.1)"}`,borderRadius:openSections[key]?"3px 3px 0 0":"3px",transition:"all .2s"}}
                onClick={()=>toggleSection(key)}>
                <div style={{display:"flex",alignItems:"center",gap:".7rem"}}>
                  <span style={{fontSize:"1rem"}}>{icon}</span>
                  <div>
                    <div style={{fontSize:".85rem",fontWeight:500,color:"var(--warm)"}}>{label}</div>
                    {!openSections[key] && <div style={{fontSize:".68rem",color:"rgba(253,250,246,.38)",marginTop:".1rem"}}>{summary}</div>}
                  </div>
                </div>
                <span style={{fontSize:"1rem",color:"var(--amber)",transition:"transform .2s",display:"inline-block",transform:openSections[key]?"rotate(180deg)":"rotate(0deg)"}}>▾</span>
              </div>
              {/* Body */}
              {openSections[key] && (
                <div style={{border:"1px solid rgba(200,133,42,.2)",borderTop:"none",borderRadius:"0 0 3px 3px",padding:"1.2rem",background:"rgba(253,250,246,.03)"}}>
                  {content}
                </div>
              )}
            </div>
          ))}

          <div className="admacts" style={{marginTop:"1.2rem"}}>
            <button className="bag">Annulla</button>
            <button className="baf" onClick={()=>alert("Impostazioni salvate!")}>💾 Salva impostazioni</button>
          </div>
        </>}
      </div>
    </div>
  );
}

/* ─── APP ─── */
export default function App() {
  const [page, setPage] = useState("home");
  const [selItem, setSelItem] = useState(null);
  const [filter, setFilter] = useState("Tutto");
  const [q, setQ] = useState("");
  const [user, setUser] = useState(null);
  const [showReg, setShowReg] = useState(false);
  const [showLogin, setShowLogin] = useState(false);
  const [showSell, setShowSell] = useState(false);
  // Shared user registry — populated by registrations, passed to AdminPanel
  const [registeredUsers, setRegisteredUsers] = useState([
    {id:"U001",name:"Marco Conti",email:"m.conti@mail.it",type:"venditore",status:"attivo",regDate:"12/01/2025",lastLogin:"08/03/2026",phone:"+39 333 1234567",taxCode:"CNTMRC85A01H501Z",iban:"IT60 X054 2811 1010 0000 0111 222",verified:true,aste:7,offerte:12,cauzioni:0},
    {id:"U002",name:"Francesca Bianchi",email:"f.bianchi@mail.it",type:"venditore",status:"sospeso",regDate:"03/02/2025",lastLogin:"01/03/2026",phone:"+39 347 9876543",taxCode:"BNCFNC92B41F205X",iban:"IT60 X054 2811 1010 0000 0222 333",verified:false,aste:0,offerte:5,cauzioni:1},
    {id:"U003",name:"Luca Verdi",email:"l.verdi@mail.it",type:"venditore",status:"attivo",regDate:"20/11/2024",lastLogin:"07/03/2026",phone:"+39 366 5554433",taxCode:"VRDLCU88C15L219K",iban:"IT60 X054 2811 1010 0000 0333 444",verified:true,aste:3,offerte:22,cauzioni:2},
    {id:"U004",name:"Sofia Russo",email:"s.russo@mail.it",type:"acquirente",status:"attivo",regDate:"14/03/2025",lastLogin:"09/03/2026",phone:"+39 320 1112233",taxCode:"",iban:"",verified:true,aste:0,offerte:34,cauzioni:3},
    {id:"U005",name:"Giorgio Mori",email:"g.mori@mail.it",type:"acquirente",status:"bloccato",regDate:"05/06/2025",lastLogin:"15/02/2026",phone:"+39 388 7778899",taxCode:"",iban:"",verified:false,aste:0,offerte:2,cauzioni:0},
    {id:"U006",name:"G. Martinelli",email:"g.martinelli@mail.it",type:"venditore",status:"attivo",regDate:"10/09/2024",lastLogin:"06/03/2026",phone:"+39 335 4445566",taxCode:"MRTGNN75D20F205R",iban:"IT60 X054 2811 1010 0000 0444 555",verified:true,aste:1,offerte:8,cauzioni:1},
    {id:"U007",name:"Elena Fontana",email:"e.fontana@mail.it",type:"acquirente",status:"attivo",regDate:"28/01/2026",lastLogin:"09/03/2026",phone:"+39 342 6667788",taxCode:"",iban:"",verified:true,aste:0,offerte:19,cauzioni:2},
  ]);

  const handleRegister = (regData) => {
    const today = new Date();
    const pad = n => String(n).padStart(2,"0");
    const dateStr = `${pad(today.getDate())}/${pad(today.getMonth()+1)}/${today.getFullYear()}`;
    const newId = "U" + String(Math.floor(Math.random()*9000)+1000);
    const newUser = {
      id: newId,
      name: regData.name,
      email: regData.email,
      type: regData.isSeller ? "venditore" : "acquirente",
      status: regData.isSeller ? "pending" : "attivo",
      regDate: dateStr,
      lastLogin: dateStr,
      phone: regData.phone || "",
      taxCode: regData.taxCode || "",
      iban: regData.iban || "",
      verified: !regData.isSeller,
      docFileName: regData.docFileName || '',
      docDataUrl: regData.docDataUrl || null,
      docMime: regData.docMime || '',
      entityType: regData.entityType || 'privato',
      indirizzo: regData.indirizzo || '',
      cap: regData.cap || '',
      citta: regData.citta || '',
      provincia: regData.provincia || '',
      pec: regData.pec || '',
      sdi: regData.sdi || '0000000',
      companyName: regData.companyName || '',
      piva: regData.piva || '',
      legalRepName: regData.legalRepName || '',
      legalRepRole: regData.legalRepRole || '',
      visuraFileName: regData.visuraFileName || '',
      visuraDataUrl: regData.visuraDataUrl || null,
      visuraMime: regData.visuraMime || '',
      aste: 0, offerte: 0, cauzioni: 0,
    };
    setRegisteredUsers(prev => [...prev, newUser]);
    setUser({ name: regData.name, email: regData.email, isSeller: regData.isSeller });
  };

  const cats = ["Tutto","Arte","Arredamento","Elettronica","Abbigliamento","Immobili","Lotto"];
  const items = ITEMS.filter(i => {
    const mf = filter==="Tutto"||(filter==="Lotto"?i.lot:i.cat===filter);
    const mq = i.title.toLowerCase().includes(q.toLowerCase());
    return mf && mq;
  });

  if(page==="admin") return (
    <div>
      <style>{CSS}</style>
      <AdminPanel onBack={()=>setPage("home")} registeredUsers={registeredUsers} setRegisteredUsers={setRegisteredUsers}/>
    </div>
  );

  return (
    <div>
      <style>{CSS}</style>

      {/* NAV */}
      <nav className="nav">
        <Logo/>
        <div className="nav-links">
          <a>Aste in corso</a>
          <a>Lotti</a>
          <a>Come funziona</a>
          <a onClick={()=>{ if(user?.isSeller) setShowSell(true); else setShowReg(true); }}>Vendi</a>
        </div>
        <div className="nav-actions">
          {user ? (
            <>
              <div className="user-chip" onClick={()=>{ if(user?.isSeller) setShowSell(true); else alert("Aggiorna account a Venditore per mettere oggetti in vendita."); }}>
                <div className="avatar">{user.name[0].toUpperCase()}</div>
                {user.name.split(" ")[0]}
                {user.isSeller && <span style={{fontSize:".62rem",marginLeft:".2rem",color:"var(--green)"}}>✓ Venditore</span>}
              </div>
              <button className="btn-ghost" style={{color:"var(--amber)",borderColor:"var(--amber)"}} onClick={()=>{ if(user?.isSeller) setShowSell(true); }}>+ Vendi</button>
              <button className="btn-ghost" onClick={()=>setUser(null)}>Esci</button>
            </>
          ) : (
            <>
              <button className="btn-ghost" onClick={()=>setShowLogin(true)}>Accedi</button>
              <button className="btn-primary" onClick={()=>setShowReg(true)}>Registrati</button>
            </>
          )}
        </div>
      </nav>

      {/* HERO */}
      <section className="hero">
        <div className="hero-inner">
          <div>
            <span className="hero-tag">Aste di oggetti unici tra privati</span>
            <h1>Ogni oggetto<br/>ha una <em>nuova vita</em><br/>da vivere</h1>
            <p>La piattaforma italiana per vendere e acquistare<br/>oggetti usati all'asta, tra privati verificati.</p>
            <div className="hero-acts">
              <button className="bhf">Esplora le aste</button>
              <button className="bho" onClick={()=>user?.isSeller ? setShowSell(true) : setShowReg(true)}>Metti in vendita →</button>
            </div>
          </div>
          <div className="hbox">
            <h3>Aste attive in questo momento</h3>
            <div className="sg">
              <div><div className="sn">247</div><div className="sl">Aste attive</div></div>
              <div><div className="sn">1.4K</div><div className="sl">Utenti online</div></div>
              <div><div className="sn">€ 82K</div><div className="sl">Volume mensile</div></div>
              <div><div className="sn">4.9★</div><div className="sl">Media venditori</div></div>
            </div>
            <hr className="sdiv"/>
            <div className="cdtitle">Asta in evidenza scade tra</div>
            <CD seconds={7440}/>
          </div>
        </div>
      </section>

      {/* COME FUNZIONA ROYALTY — banner */}
      <div style={{background:"var(--amber-p)",borderBottom:"1px solid var(--border)",padding:".7rem 2rem"}}>
        <div style={{maxWidth:"1100px",margin:"0 auto",display:"flex",alignItems:"center",justifyContent:"center",gap:"2rem",flexWrap:"wrap",fontSize:".78rem",color:"var(--char)"}}>
          <span>🔒 <strong>Prezzo di riserva</strong> garantito</span>
          <span style={{color:"var(--border)"}}>|</span>
          <span>🪪 <strong>Venditori verificati</strong></span>
        </div>
      </div>

      {/* SEARCH */}
      <div className="sbar">
        <div className="sbar-in">
          <div className="sbox">
            <span style={{color:"var(--muted)"}}>🔍</span>
            <input placeholder="Cerca oggetti, categorie, lotti..." value={q} onChange={e=>setQ(e.target.value)}/>
          </div>
          <div className="pills">
            {cats.map(c=><button key={c} className={`pill ${filter===c?"on":""}`} onClick={()=>setFilter(c)}>{c}</button>)}
          </div>
        </div>
      </div>

      {/* MAIN */}
      <main className="main">
        {user && <div className="welc">
          <div>
            <div style={{fontFamily:"'Cormorant Garamond',serif",fontSize:"1.2rem"}}>Bentornato, <em>{user.name.split(" ")[0]}</em> 👋</div>
            <div style={{fontSize:".78rem",color:"var(--muted)",marginTop:".25rem"}}>
              {user.isSeller ? `Account venditore attivo · Vendere è gratuito per te` : "Account acquirente · Vuoi vendere? Attiva l'account venditore."}
            </div>
          </div>
          {user.isSeller
            ? <button className="btn-primary" onClick={()=>setShowSell(true)}>+ Nuova asta</button>
            : <button className="btn-ghost" onClick={()=>setShowReg(true)}>Diventa venditore →</button>}
        </div>}

        <div className="sh">
          <h2 className="st">Aste <span>in corso</span></h2>
          <span className="sl2">Vedi tutte →</span>
        </div>
        {items.length===0
          ? <div className="empty">Nessun risultato per la ricerca "{q}".</div>
          : <div className="grid">{items.map(it=><ItemCard key={it.id} item={it} onClick={()=>setSelItem(it)}/>)}</div>}
      </main>

      {/* FOOTER */}
      <footer className="footer">
        <div className="fin">
          <div>
            <Logo size={40} textSize="1.32rem" dark/>
            <p className="ftag">La piattaforma italiana di aste tra privati.<br/>Pezzi unici, storie autentiche, prezzi onesti.<br/>Venditori verificati.</p>
          </div>
          <div className="fcol">
            <h4>Per gli acquirenti</h4>
            <a>Come fare offerte</a><a>Autobid</a><a>Watchlist</a><a>Sicurezza</a>
          </div>
          <div className="fcol">
            <h4>Per i venditori</h4>
            <a>Metti in vendita</a><a>Gestisci lotti</a><a>Prezzo di riserva</a><a>Come funzionano le commissioni</a>
          </div>
          <div className="fcol">
            <h4>Battilo</h4>
            <a>Chi siamo</a><a>Blog</a><a>Privacy</a><a>Contatti</a>
          </div>
        </div>
        <div className="fbot">
          <span>© 2025 Battilo S.r.l. · P.IVA IT12345678901 · Milano, Italia</span>
          <span>Battilo · Piattaforma aste e vendite tra privati verificati</span>
        </div>
      </footer>

      {/* MODALS */}
      {selItem && <DetailModal item={selItem} onClose={()=>setSelItem(null)}/>}
      {showReg && <RegisterModal onClose={()=>setShowReg(false)} onSuccess={handleRegister}/>}
      {showSell && user?.isSeller && <SellModal user={user} onClose={()=>setShowSell(false)}/>}

      {/* LOGIN RAPIDO DEMO */}
      {showLogin && (
        <div className="ov" onClick={()=>setShowLogin(false)}>
          <div className="lmodal" onClick={e=>e.stopPropagation()}>
            <div className="mhdr"><h2>Accedi a Battilo</h2><button className="mcl" onClick={()=>setShowLogin(false)}>✕</button></div>
            <div className="regbody">
              <div className="fg"><label className="fl">Email</label><input className="fi" type="email" placeholder="tuaemail@esempio.it"/></div>
              <div className="fg"><label className="fl">Password</label><input className="fi" type="password" placeholder="••••••••"/></div>
              <div style={{display:"flex",justifyContent:"space-between",alignItems:"center",marginTop:"1rem"}}>
                <span style={{fontSize:".75rem",color:"var(--amber)",cursor:"pointer"}}>Password dimenticata?</span>
                <button className="snext" onClick={()=>{ setUser({name:"Marco Conti",email:"m.conti@mail.it",isSeller:true}); setShowLogin(false); }}>
                  Accedi →
                </button>
              </div>
              <div style={{textAlign:"center",marginTop:"1.4rem",fontSize:".78rem",color:"var(--muted)"}}>
                Non hai un account? <span style={{color:"var(--amber)",cursor:"pointer",fontWeight:500}} onClick={()=>{setShowLogin(false);setShowReg(true);}}>Registrati gratuitamente</span>
              </div>
              <div style={{marginTop:".8rem",padding:".65rem",background:"var(--cream)",border:"1px dashed var(--border)",borderRadius:"2px",fontSize:".72rem",color:"var(--muted)",textAlign:"center"}}>
                Demo: clicca "Accedi" per simulare il login come venditore verificato
              </div>
            </div>
          </div>
        </div>
      )}

      {/* PAGE SWITCHER */}
      <div className="psw">
        <button className={`pb pbl ${page==="home"?"sel":""}`} onClick={()=>setPage("home")}>🏠 Sito</button>
        <button className={`pb pbd ${page==="admin"?"sel":""}`} onClick={()=>setPage("admin")}>⚙️ Admin</button>
      </div>
    </div>
  );
}
