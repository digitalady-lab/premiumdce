import { useState, useEffect, useRef } from "react";

const AMBER = "#F59E0B";
const RED = "#EF4444";
const TEAL = "#14B8A6";
const BG = "#0A0A0A";
const CARD = "#141414";
const CARD_ALT = "#1A1A1A";
const BORDER = "#262626";
const WHITE = "#F5F5F5";
const GRAY = "#9CA3AF";
const GRAY_DIM = "#4B5563";

const sections = [
  { id: "intro", label: "Bevezető", icon: "⚡" },
  { id: "theory", label: "Elmélet", icon: "🧠" },
  { id: "levels", label: "3 Szint", icon: "📊" },
  { id: "dental", label: "Fogászat", icon: "🦷" },
  { id: "webshop", label: "Webshop", icon: "🛒" },
  { id: "action", label: "Akcióterv", icon: "🎯" },
  { id: "prompts", label: "Promptok", icon: "💬" },
  { id: "tools", label: "Eszközök", icon: "🔧" },
];

const todos = [
  { num: "01", title: "VÁLASZD KI A CÉLPIACOD", desc: "Döntsd el: melyik iparágnak/cégnek akarsz AI-marketing szolgáltatást nyújtani? Írj le 3 konkrét céget a környezetedből (fogászat, webshop, edző, stb.).", time: "15 perc" },
  { num: "02", title: "FUTTASD A MASTER PROMPTOT", desc: "Nyisd meg a ChatGPT-t vagy Claude-ot. Másold be a lecke Master Prompt-ját, de cseréld ki a [termékkategória]-t a TE célpiacod iparágára. Mentsd el az eredményt.", time: "10 perc" },
  { num: "03", title: "VALIDÁLD A FÁJDALOMPONTOKAT", desc: "Menj el a célpiacod online közösségeibe (Facebook-csoportok, Reddit, fórumok). Keresd meg, hogy a valódi emberek TÉNYLEG ezekről panaszkodnak-e. Jegyzetelj.", time: "30 perc" },
  { num: "04", title: "KÉSZÍTSD EL A FÁJDALOM-TÉRKÉPET", desc: "Rajzolj egy 3 oszlopos táblázatot (Felszíni / Érzelmi / Identitás). Töltsd fel a validált fájdalompontokkal. Ez lesz az ÖSSZES tartalomgyártásod alapja.", time: "20 perc" },
  { num: "05", title: "ÍRJ 3 HOOK-OT", desc: "A fájdalom-térkép alapján írj 3 videó-nyitómondatot (hook-ot), amelyik az ÉRZELMI szintet célozza. Teszteld: ha te látnád ezt a Reels-en, megállnál?", time: "15 perc" },
  { num: "06", title: "KÜLDD EL EGY ISMERŐS CÉGNEK", desc: "Válassz ki 1 céget a listádról. Írd meg nekik: „Csináltam egy felmérést a célközönséged fájdalompontjairól — ingyen megmutatom." Ez az ügyfélszerzés első lépése.", time: "20 perc" },
];

const prompts = [
  {
    id: "p1",
    title: "CÉLKÖZÖNSÉG-KUTATÁS",
    tag: "PROMPT #1",
    text: `Szereped: piacvezető marketing stratéga. A [IPARÁG] szektorban dolgozom. Készíts egy részletes célközönség-profilt, amely tartalmazza: (1) demográfiai adatok, (2) top 5 félelem és frusztráció, (3) top 5 vágy és aspiráció, (4) milyen kifejezéseket használnak online a problémáikra (szó szerinti idézetek stílusában), (5) hol töltik az idejüket online. Legyél szájbarágós, adj konkrét példákat.`,
  },
  {
    id: "p2",
    title: "HOOK GENERÁTOR",
    tag: "PROMPT #2",
    text: `A célközönségem: [CÉLKÖZÖNSÉG LEÍRÁS]. A fő fájdalompontjuk: [FÁJDALOMPONT]. Generálj 10 videó-nyitómondatot (hook-ot), amelyek: (1) max 8 szavak, (2) érzelmi reakciót váltanak ki (félelem, kíváncsiság, felháborodás, azonosulás), (3) a célközönség saját szavaival szólnak, nem marketing-nyelven. Adj minden hook-hoz egy rövid magyarázatot, hogy melyik pszichológiai triggert használja.`,
  },
  {
    id: "p3",
    title: "FÁJDALOMPONT VALIDÁCIÓ",
    tag: "PROMPT #3",
    text: `Elemezd ezeket a fájdalompontokat a [IPARÁG] szektorban: [LISTA]. Minden pontnál értékeld 1-10-ig: (1) Mennyire gyakori? (2) Mennyire intenzív az érzelmi töltete? (3) Mennyire pénzesíthető (hajlandó fizetni a megoldásért)? Rangsorold a legértékesebb fájdalomponttól a legkevésbé értékesig. A TOP 3-ból mindegyikhez adj egy konkrét videó-tartalom ötletet.`,
  },
];

function CopyButton({ text }) {
  const [copied, setCopied] = useState(false);
  return (
    <button
      onClick={() => {
        navigator.clipboard.writeText(text).then(() => {
          setCopied(true);
          setTimeout(() => setCopied(false), 2000);
        });
      }}
      style={{
        background: copied ? TEAL : "rgba(245,158,11,0.15)",
        border: `1px solid ${copied ? TEAL : "rgba(245,158,11,0.3)"}`,
        color: copied ? BG : AMBER,
        padding: "8px 18px",
        borderRadius: 6,
        cursor: "pointer",
        fontSize: 12,
        fontFamily: "'JetBrains Mono', monospace",
        fontWeight: 700,
        letterSpacing: "0.05em",
        transition: "all 0.3s ease",
        display: "flex",
        alignItems: "center",
        gap: 6,
      }}
    >
      {copied ? "✓ MÁSOLVA" : "MÁSOLÁS"}
    </button>
  );
}

function Tag({ children, color = AMBER }) {
  return (
    <span
      style={{
        background: color,
        color: BG,
        padding: "4px 12px",
        borderRadius: 4,
        fontSize: 11,
        fontWeight: 800,
        fontFamily: "'JetBrains Mono', monospace",
        letterSpacing: "0.08em",
        display: "inline-block",
      }}
    >
      {children}
    </span>
  );
}

function PainLevel({ name, color, quotes, comment }) {
  const [open, setOpen] = useState(false);
  return (
    <div
      style={{
        background: CARD,
        borderRadius: 10,
        border: `1px solid ${open ? color : BORDER}`,
        overflow: "hidden",
        transition: "all 0.3s ease",
        marginBottom: 12,
      }}
    >
      <button
        onClick={() => setOpen(!open)}
        style={{
          width: "100%",
          background: "transparent",
          border: "none",
          padding: "16px 20px",
          cursor: "pointer",
          display: "flex",
          alignItems: "center",
          justifyContent: "space-between",
        }}
      >
        <div style={{ display: "flex", alignItems: "center", gap: 12 }}>
          <div
            style={{
              width: 10,
              height: 10,
              borderRadius: "50%",
              background: color,
              boxShadow: `0 0 12px ${color}60`,
            }}
          />
          <span
            style={{
              color: WHITE,
              fontFamily: "'JetBrains Mono', monospace",
              fontSize: 13,
              fontWeight: 700,
              letterSpacing: "0.06em",
            }}
          >
            {name} SZINT
          </span>
        </div>
        <span
          style={{
            color: GRAY_DIM,
            fontSize: 18,
            transform: open ? "rotate(180deg)" : "rotate(0)",
            transition: "transform 0.3s ease",
          }}
        >
          ▾
        </span>
      </button>
      {open && (
        <div style={{ padding: "0 20px 20px" }}>
          {quotes.map((q, i) => (
            <div
              key={i}
              style={{
                padding: "10px 16px",
                background: "rgba(255,255,255,0.03)",
                borderLeft: `3px solid ${color}40`,
                borderRadius: "0 6px 6px 0",
                marginBottom: 8,
                fontStyle: "italic",
                color: GRAY,
                fontSize: 14,
                lineHeight: 1.5,
              }}
            >
              „{q}"
            </div>
          ))}
          <p
            style={{
              color,
              fontSize: 13,
              fontWeight: 600,
              marginTop: 12,
              lineHeight: 1.6,
            }}
          >
            → {comment}
          </p>
        </div>
      )}
    </div>
  );
}

export default function KnowledgeBase() {
  const [activeSection, setActiveSection] = useState("intro");
  const [completedTodos, setCompletedTodos] = useState({});
  const [sidebarOpen, setSidebarOpen] = useState(false);
  const [scrollY, setScrollY] = useState(0);
  const mainRef = useRef(null);

  useEffect(() => {
    const el = mainRef.current;
    if (!el) return;
    const handleScroll = () => {
      setScrollY(el.scrollTop);
      const sectionEls = sections.map((s) => document.getElementById(s.id));
      for (let i = sectionEls.length - 1; i >= 0; i--) {
        if (sectionEls[i] && sectionEls[i].getBoundingClientRect().top < 200) {
          setActiveSection(sections[i].id);
          break;
        }
      }
    };
    el.addEventListener("scroll", handleScroll);
    return () => el.removeEventListener("scroll", handleScroll);
  }, []);

  const completedCount = Object.values(completedTodos).filter(Boolean).length;
  const progress = (completedCount / todos.length) * 100;

  const scrollTo = (id) => {
    document.getElementById(id)?.scrollIntoView({ behavior: "smooth" });
    setSidebarOpen(false);
  };

  const sectionStyle = { maxWidth: 760, margin: "0 auto", padding: "60px 20px" };
  const h2Style = {
    fontSize: "clamp(28px, 5vw, 42px)",
    fontWeight: 900,
    color: WHITE,
    lineHeight: 1.1,
    margin: 0,
    letterSpacing: "-0.02em",
  };
  const bodyStyle = { color: GRAY, fontSize: 15, lineHeight: 1.75, margin: "16px 0" };

  return (
    <div style={{ background: BG, minHeight: "100vh", fontFamily: "'Outfit', 'Segoe UI', sans-serif" }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700;800&family=Outfit:wght@300;400;600;700;900&display=swap');
        * { box-sizing: border-box; margin: 0; padding: 0; }
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: ${BG}; }
        ::-webkit-scrollbar-thumb { background: ${BORDER}; border-radius: 3px; }
        ::selection { background: ${AMBER}40; color: ${WHITE}; }
        @keyframes fadeUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes pulseGlow { 0%, 100% { box-shadow: 0 0 20px ${AMBER}20; } 50% { box-shadow: 0 0 40px ${AMBER}40; } }
        @keyframes slideIn { from { opacity: 0; transform: translateX(-20px); } to { opacity: 1; transform: translateX(0); } }
        .fade-up { animation: fadeUp 0.6s ease forwards; }
        .sidebar-item:hover { background: rgba(245,158,11,0.08) !important; }
        .todo-card:hover { border-color: ${AMBER}60 !important; }
        .prompt-card:hover { border-color: ${AMBER} !important; transform: translateY(-2px); }
      `}</style>

      {/* Mobile menu button */}
      <button
        onClick={() => setSidebarOpen(!sidebarOpen)}
        style={{
          position: "fixed",
          top: 16,
          left: 16,
          zIndex: 1000,
          background: CARD,
          border: `1px solid ${BORDER}`,
          borderRadius: 8,
          width: 44,
          height: 44,
          display: "none",
          alignItems: "center",
          justifyContent: "center",
          cursor: "pointer",
          color: AMBER,
          fontSize: 20,
        }}
        className="mobile-menu-btn"
      >
        {sidebarOpen ? "✕" : "☰"}
      </button>
      <style>{`@media (max-width: 860px) { .mobile-menu-btn { display: flex !important; } .sidebar { transform: translateX(${sidebarOpen ? "0" : "-100%"}) !important; position: fixed !important; z-index: 999 !important; } }`}</style>

      {/* Sidebar */}
      <nav
        className="sidebar"
        style={{
          position: "fixed",
          top: 0,
          left: 0,
          width: 240,
          height: "100vh",
          background: "#0D0D0D",
          borderRight: `1px solid ${BORDER}`,
          display: "flex",
          flexDirection: "column",
          zIndex: 999,
          transition: "transform 0.3s ease",
        }}
      >
        <div style={{ padding: "24px 20px 16px", borderBottom: `1px solid ${BORDER}` }}>
          <div style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 10, color: AMBER, fontWeight: 800, letterSpacing: "0.12em", marginBottom: 4 }}>
            1. MODUL / 2. LECKE
          </div>
          <div style={{ fontSize: 14, fontWeight: 700, color: WHITE, lineHeight: 1.3 }}>
            Fájdalompontok feltérképezése
          </div>
        </div>

        <div style={{ flex: 1, overflowY: "auto", padding: "12px 8px" }}>
          {sections.map((s) => (
            <button
              key={s.id}
              className="sidebar-item"
              onClick={() => scrollTo(s.id)}
              style={{
                width: "100%",
                background: activeSection === s.id ? "rgba(245,158,11,0.12)" : "transparent",
                border: "none",
                borderRadius: 8,
                padding: "10px 12px",
                cursor: "pointer",
                display: "flex",
                alignItems: "center",
                gap: 10,
                marginBottom: 2,
                transition: "all 0.2s ease",
                borderLeft: activeSection === s.id ? `3px solid ${AMBER}` : "3px solid transparent",
              }}
            >
              <span style={{ fontSize: 16 }}>{s.icon}</span>
              <span
                style={{
                  fontSize: 13,
                  fontWeight: activeSection === s.id ? 700 : 400,
                  color: activeSection === s.id ? WHITE : GRAY_DIM,
                  textAlign: "left",
                }}
              >
                {s.label}
              </span>
            </button>
          ))}
        </div>

        {/* Progress */}
        <div style={{ padding: "16px 20px", borderTop: `1px solid ${BORDER}` }}>
          <div style={{ display: "flex", justifyContent: "space-between", marginBottom: 8 }}>
            <span style={{ fontSize: 10, fontFamily: "'JetBrains Mono', monospace", color: GRAY_DIM, fontWeight: 700, letterSpacing: "0.08em" }}>
              HALADÁS
            </span>
            <span style={{ fontSize: 10, fontFamily: "'JetBrains Mono', monospace", color: AMBER, fontWeight: 700 }}>
              {completedCount}/{todos.length}
            </span>
          </div>
          <div style={{ height: 4, background: BORDER, borderRadius: 2, overflow: "hidden" }}>
            <div style={{ height: "100%", width: `${progress}%`, background: AMBER, borderRadius: 2, transition: "width 0.5s ease" }} />
          </div>
        </div>
      </nav>

      {/* Main content */}
      <main
        ref={mainRef}
        style={{
          marginLeft: 240,
          height: "100vh",
          overflowY: "auto",
          overflowX: "hidden",
        }}
      >
        <style>{`@media (max-width: 860px) { main { margin-left: 0 !important; } }`}</style>

        {/* HERO */}
        <section id="intro" style={{ position: "relative", minHeight: "80vh", display: "flex", alignItems: "center", overflow: "hidden" }}>
          <div style={{ position: "absolute", top: 0, left: 0, right: 0, height: 4, background: AMBER }} />
          <div
            style={{
              position: "absolute",
              right: -80,
              top: "50%",
              transform: "translateY(-50%)",
              fontSize: "clamp(200px, 30vw, 360px)",
              fontWeight: 900,
              color: "rgba(245,158,11,0.04)",
              fontFamily: "'Outfit', sans-serif",
              lineHeight: 1,
              pointerEvents: "none",
              userSelect: "none",
            }}
          >
            02
          </div>
          <div style={{ ...sectionStyle, position: "relative", zIndex: 1 }} className="fade-up">
            <Tag>1. MODUL / 2. LECKE</Tag>
            <h1
              style={{
                fontSize: "clamp(36px, 7vw, 64px)",
                fontWeight: 900,
                color: WHITE,
                lineHeight: 1.05,
                marginTop: 24,
                letterSpacing: "-0.03em",
              }}
            >
              A célközönség
              <br />
              fájdalompontjainak
              <br />
              feltérképezése
              <br />
              <span style={{ color: AMBER }}>AI segítségével</span>
            </h1>
            <div style={{ width: 80, height: 3, background: AMBER, margin: "28px 0", borderRadius: 2 }} />
            <p style={{ color: GRAY, fontSize: 17, lineHeight: 1.7, maxWidth: 520 }}>
              Nem szép videókat gyártunk. Fájdalomra építünk és eladunk.
              Ez a lecke megtanít arra, hogyan használd az AI-t arra, hogy
              <strong style={{ color: WHITE }}> megértsd, mi fáj a vásárlódnak</strong> — és
              hogyan váltsd azt pénzre.
            </p>
          </div>
        </section>

        {/* THEORY */}
        <section id="theory" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag color={RED}>ELMÉLET</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Miért nem érdekli senkit
              <br />
              <span style={{ color: RED }}>a te terméked?</span>
            </h2>
            <div style={{ width: 60, height: 3, background: RED, margin: "20px 0", borderRadius: 2 }} />
            <p style={bodyStyle}>
              Brutális igazság: a vásárlódat hidegen hagyja, hogy milyen szép a videód,
              milyen menő a logód, vagy milyen okos a szlogened. Egyetlen dolgot akar tudni:
              <strong style={{ color: WHITE }}> „Ez megoldja a PROBLÉMÁMAT?"</strong> Ha nem értesz a fájdalmához,
              nem tudsz eladni neki. Pont.
            </p>
            <p style={bodyStyle}>
              A legtöbb AI-videós azt gondolja, hogy a technológia az eladási érv.
              „Nézd, milyen élethű AI-avatar!" — mondják. A vásárló meg tovább görget. Mert nem
              a technológia érdekli, hanem az, hogy <strong style={{ color: WHITE }}>TE értsd, mi fáj neki hajnali
              3-kor</strong>, amikor nem tud aludni az üzleti problémái miatt.
            </p>

            {/* Key concept card */}
            <div
              style={{
                background: CARD,
                borderRadius: 12,
                borderLeft: `4px solid ${RED}`,
                padding: "24px 28px",
                marginTop: 28,
              }}
            >
              <div style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 11, fontWeight: 800, color: RED, letterSpacing: "0.08em", marginBottom: 12 }}>
                KULCSFOGALOM: FÁJDALOMPONT (PAIN POINT)
              </div>
              <p style={{ color: GRAY, fontSize: 14, lineHeight: 1.7, fontStyle: "italic" }}>
                A fájdalompont nem az, amit TE gondolsz a vásárlód problémájáról.
                A fájdalompont az, amit a <strong style={{ color: WHITE }}>VÁSÁRLÓ érez</strong> — a frusztráció,
                a félelem, az álmatlan éjszakák. Az AI segítségével feltérképezheted ezeket
                a valódi, nyers érzelmeket, nem csak a felszínt.
              </p>
            </div>
          </div>
        </section>

        {/* 3 LEVELS */}
        <section id="levels" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag>3 SZINT</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              A fájdalompont-feltérképezés
              <br />
              <span style={{ color: AMBER }}>3 szintje</span>
            </h2>
            <div style={{ width: 40, height: 2, background: AMBER, margin: "20px 0", borderRadius: 2 }} />

            {[
              {
                num: "01",
                title: "FELSZÍNI FÁJDALOM",
                color: GRAY,
                desc: "Amit a vásárló mond.",
                detail: '„Kevés az ügyfelem." „Drága a hirdetés." Ezt mindenki hallja. Ez NEM elég az eladáshoz.',
              },
              {
                num: "02",
                title: "ÉRZELMI FÁJDALOM",
                color: AMBER,
                desc: "Amit a vásárló érez.",
                detail: '„Félek, hogy csődbe megyek." „Szégyellem, hogy nem megy." Ez az, ami igazán motivál.',
              },
              {
                num: "03",
                title: "IDENTITÁS-FÁJDALOM",
                color: RED,
                desc: "Amit a vásárló LENNI akar.",
                detail: '„Sikeres vállalkozó szeretnék lenni." „Azt akarom, hogy tiszteljenek." EZ az arany.',
              },
            ].map((level) => (
              <div
                key={level.num}
                style={{
                  display: "flex",
                  gap: 20,
                  alignItems: "flex-start",
                  padding: "24px 0",
                  borderBottom: `1px solid ${BORDER}`,
                }}
              >
                <span
                  style={{
                    fontFamily: "'Outfit', sans-serif",
                    fontSize: 48,
                    fontWeight: 900,
                    color: level.color,
                    lineHeight: 1,
                    minWidth: 60,
                    opacity: level.color === GRAY ? 0.4 : 1,
                  }}
                >
                  {level.num}
                </span>
                <div>
                  <div style={{ fontSize: 16, fontWeight: 700, color: WHITE, marginBottom: 6 }}>{level.title}</div>
                  <div style={{ fontSize: 13, color: level.color, fontWeight: 600, marginBottom: 4 }}>{level.desc}</div>
                  <div style={{ fontSize: 14, color: GRAY, lineHeight: 1.6 }}>{level.detail}</div>
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* DENTAL */}
        <section id="dental" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag color={TEAL}>ESETTANULMÁNY</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Fogászat
              <br />
              <span style={{ color: TEAL }}>— a rejtett fájdalmak</span>
            </h2>
            <div style={{ width: 50, height: 2, background: TEAL, margin: "20px 0", borderRadius: 2 }} />
            <p style={bodyStyle}>
              A legtöbb fogorvos úgy hirdeti magát: „Modern eszközök, kedves személyzet,
              fájdalommentes kezelés." Gratulálok, ezt a szöveget <strong style={{ color: WHITE }}>MINDENKI</strong> írja.
              Nézzük, mit mond valójában a páciens, amikor este a Google-be gépel:
            </p>

            <div style={{ marginTop: 20 }}>
              <PainLevel
                name="FELSZÍNI"
                color={GRAY}
                quotes={[
                  "Mennyibe kerül egy korona?",
                  "Melyik a legjobb fogorvos a közelemben?",
                  "Fogfehérítés árak 2025",
                ]}
                comment="Ezekre MINDENKI céloz hirdetéssel. Drága kattintás, alacsony konverzió."
              />
              <PainLevel
                name="ÉRZELMI"
                color={AMBER}
                quotes={[
                  "Rettegek a fogorvostól, de fáj a fogam.",
                  "Szégyellem a fogaimat, nem merek mosolyogni.",
                  "Félek, hogy ítélkezni fognak, mert évek óta nem voltam.",
                ]}
                comment="ITT kezdődik az igazi marketing. Ezekre az érzelmekre kell építeni."
              />
              <PainLevel
                name="IDENTITÁS"
                color={RED}
                quotes={[
                  "Azt akarom, hogy magabiztosan mosolyogjak egy állásinterjún.",
                  "Nem akarok az lenni, aki eltakarja a száját fotón.",
                  "Méltó akarok lenni egy szép mosolyra.",
                ]}
                comment="EZ az arany. Ez az, amire az AI-videó sztorit építesz."
              />
            </div>

            {/* Dental prompt */}
            <div
              style={{
                background: CARD,
                borderRadius: 12,
                border: `1px solid ${BORDER}`,
                borderTop: `3px solid ${AMBER}`,
                padding: "24px",
                marginTop: 28,
              }}
            >
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 16 }}>
                <span style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 11, fontWeight: 800, color: AMBER, letterSpacing: "0.06em" }}>
                  ⚡ MASTER PROMPT — FOGÁSZAT
                </span>
                <CopyButton
                  text={`Te egy marketing pszichológus vagy. Listázd ki egy fogászati rendelő potenciális pácienseinek TOP 10 fájdalompontját 3 szinten: (1) Felszíni — amit Google-be gépelnek, (2) Érzelmi — amit éjszaka éreznek, (3) Identitás — akivé válni akarnak. Minden ponthoz írj egy 1 mondatos hook-ot, ami megállítja a görgetést egy TikTok videóban. Legyél nyers, emberi, ne marketinges.`}
                />
              </div>
              <p style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 12.5, color: GRAY, lineHeight: 1.8 }}>
                Te egy marketing pszichológus vagy. Listázd ki egy fogászati rendelő potenciális
                pácienseinek TOP 10 fájdalompontját 3 szinten: (1) Felszíni — amit Google-be gépelnek,
                (2) Érzelmi — amit éjszaka éreznek, (3) Identitás — akivé válni akarnak. Minden ponthoz
                írj egy 1 mondatos hook-ot, ami megállítja a görgetést egy TikTok videóban. Legyél nyers,
                emberi, ne marketinges.
              </p>
            </div>
          </div>
        </section>

        {/* WEBSHOP */}
        <section id="webshop" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag color={TEAL}>ESETTANULMÁNY</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Webshop
              <br />
              <span style={{ color: TEAL }}>— miért nem vásárolnak?</span>
            </h2>
            <div style={{ width: 50, height: 2, background: TEAL, margin: "20px 0", borderRadius: 2 }} />
            <p style={bodyStyle}>
              Egy webshop tulaj azt mondja: „Futtatom a hirdetéseket, jön a forgalom, de nem
              vesznek." Klasszikus eset. A probléma: nem a terméket próbálja eladni, hanem a
              <strong style={{ color: WHITE }}> vásárló problémáját kellene megoldania</strong>. Nézzük a 3 szintet:
            </p>

            <div style={{ marginTop: 20 }}>
              <PainLevel
                name="FELSZÍNI"
                color={GRAY}
                quotes={[
                  "Keresek egy jó [termékkategória]-t online.",
                  "Melyik a legjobb ár-érték arányú?",
                  "Van ingyenes szállítás?",
                ]}
                comment="Árérzékeny, összehasonlító vásárló. Ide versenyzik mindenki — véres verseny."
              />
              <PainLevel
                name="ÉRZELMI"
                color={AMBER}
                quotes={[
                  "Már háromszor rendeltem rossz minőséget, idegesít.",
                  "Félek, hogy átvernek, visszaküldeni macerás.",
                  "Úgy érzem, soha nem találok olyat, ami tényleg jó.",
                ]}
                comment="A bizalomhiány és a korábbi rossz tapasztalatok. IDE kell célozni a videóval."
              />
              <PainLevel
                name="IDENTITÁS"
                color={RED}
                quotes={[
                  "Olyan embernek akarok tűnni, akinek jó ízlése van.",
                  "Azt akarom, hogy lássák: nem a legolcsóbbat választom.",
                  "Tudatos vásárló szeretnék lenni, nem impulzív.",
                ]}
                comment="Az önkép, amit a vásárlás megerősít. EZ konvertál long-term."
              />
            </div>

            {/* Webshop prompt */}
            <div
              style={{
                background: CARD,
                borderRadius: 12,
                border: `1px solid ${BORDER}`,
                borderTop: `3px solid ${AMBER}`,
                padding: "24px",
                marginTop: 28,
              }}
            >
              <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 16 }}>
                <span style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 11, fontWeight: 800, color: AMBER, letterSpacing: "0.06em" }}>
                  ⚡ MASTER PROMPT — WEBSHOP
                </span>
                <CopyButton
                  text={`Te egy e-commerce konverziós szakértő vagy. Egy [termékkategória] webshop számára tárj fel 10 vásárlói fájdalompontot 3 szinten: (1) Felszíni — amit keresnek, (2) Érzelmi — ami frusztrálja őket a vásárlásban, (3) Identitás — amilyen vásárlóvá válni akarnak. Minden ponthoz adj egy 1 mondatos videó-hook ötletet, ami a „te is így érzed?" effektust kelti. Legyél közvetlen, ne használj marketing-zsargont.`}
                />
              </div>
              <p style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 12.5, color: GRAY, lineHeight: 1.8 }}>
                Te egy e-commerce konverziós szakértő vagy. Egy [termékkategória] webshop számára
                tárj fel 10 vásárlói fájdalompontot 3 szinten: (1) Felszíni — amit keresnek,
                (2) Érzelmi — ami frusztrálja őket a vásárlásban, (3) Identitás — amilyen vásárlóvá
                válni akarnak. Minden ponthoz adj egy 1 mondatos videó-hook ötletet, ami a „te is
                így érzed?" effektust kelti. Legyél közvetlen, ne használj marketing-zsargont.
              </p>
            </div>
          </div>
        </section>

        {/* ACTION PLAN */}
        <section id="action" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag color={RED}>CSELEKVÉS</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Konkrét
              <br />
              <span style={{ color: RED }}>akcióterv</span>
            </h2>
            <div style={{ width: 60, height: 3, background: RED, margin: "20px 0", borderRadius: 2 }} />
            <p style={bodyStyle}>
              Ne csak olvasd — <strong style={{ color: WHITE }}>CSINÁLD</strong>. Ez a különbség a tudás és a pénz között.
            </p>

            <div style={{ marginTop: 24 }}>
              {todos.map((todo, i) => (
                <div
                  key={todo.num}
                  className="todo-card"
                  style={{
                    background: completedTodos[i] ? "rgba(245,158,11,0.05)" : CARD,
                    borderRadius: 12,
                    border: `1px solid ${completedTodos[i] ? `${AMBER}40` : BORDER}`,
                    padding: "20px 24px",
                    marginBottom: 12,
                    transition: "all 0.3s ease",
                    cursor: "pointer",
                  }}
                  onClick={() => setCompletedTodos((p) => ({ ...p, [i]: !p[i] }))}
                >
                  <div style={{ display: "flex", alignItems: "flex-start", gap: 16 }}>
                    <div
                      style={{
                        width: 28,
                        height: 28,
                        borderRadius: 6,
                        border: `2px solid ${completedTodos[i] ? AMBER : GRAY_DIM}`,
                        background: completedTodos[i] ? AMBER : "transparent",
                        display: "flex",
                        alignItems: "center",
                        justifyContent: "center",
                        flexShrink: 0,
                        marginTop: 2,
                        transition: "all 0.3s ease",
                      }}
                    >
                      {completedTodos[i] && (
                        <span style={{ color: BG, fontSize: 16, fontWeight: 900 }}>✓</span>
                      )}
                    </div>
                    <div style={{ flex: 1 }}>
                      <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 6 }}>
                        <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
                          <span style={{ fontFamily: "'Outfit', sans-serif", fontSize: 22, fontWeight: 900, color: AMBER }}>
                            {todo.num}
                          </span>
                          <span
                            style={{
                              fontSize: 14,
                              fontWeight: 700,
                              color: completedTodos[i] ? GRAY : WHITE,
                              textDecoration: completedTodos[i] ? "line-through" : "none",
                              transition: "all 0.3s",
                            }}
                          >
                            {todo.title}
                          </span>
                        </div>
                        <span style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 11, color: GRAY_DIM, fontWeight: 700 }}>
                          {todo.time}
                        </span>
                      </div>
                      <p style={{ fontSize: 13, color: GRAY, lineHeight: 1.6, margin: 0 }}>{todo.desc}</p>
                    </div>
                  </div>
                </div>
              ))}
            </div>

            {/* Summary */}
            <div
              style={{
                background: "rgba(245,158,11,0.08)",
                borderRadius: 12,
                border: `1px solid rgba(245,158,11,0.2)`,
                padding: "20px 24px",
                marginTop: 24,
                display: "flex",
                justifyContent: "space-between",
                alignItems: "center",
                flexWrap: "wrap",
                gap: 12,
              }}
            >
              <div>
                <div style={{ fontSize: 16, fontWeight: 700, color: AMBER }}>ÖSSZESEN: ~2 ÓRA MUNKA</div>
                <div style={{ fontSize: 13, color: GRAY, marginTop: 4 }}>= Az első ügyfélszerzésed alapja</div>
              </div>
              <div style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 24, fontWeight: 900, color: AMBER }}>
                {completedCount}/{todos.length}
              </div>
            </div>
          </div>
        </section>

        {/* PROMPTS */}
        <section id="prompts" style={{ borderTop: `1px solid ${BORDER}` }}>
          <div style={sectionStyle}>
            <Tag color={AMBER}>PROMPTOK</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Copy-paste kész
              <br />
              <span style={{ color: AMBER }}>promptok</span>
            </h2>
            <div style={{ width: 50, height: 2, background: AMBER, margin: "20px 0", borderRadius: 2 }} />

            {prompts.map((p) => (
              <div
                key={p.id}
                className="prompt-card"
                style={{
                  background: CARD,
                  borderRadius: 12,
                  border: `1px solid ${BORDER}`,
                  padding: "24px",
                  marginBottom: 16,
                  transition: "all 0.3s ease",
                }}
              >
                <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center", marginBottom: 16 }}>
                  <div>
                    <span
                      style={{
                        fontFamily: "'JetBrains Mono', monospace",
                        fontSize: 10,
                        fontWeight: 800,
                        color: AMBER,
                        letterSpacing: "0.1em",
                        display: "block",
                        marginBottom: 4,
                      }}
                    >
                      {p.tag}
                    </span>
                    <span style={{ fontSize: 16, fontWeight: 700, color: WHITE }}>{p.title}</span>
                  </div>
                  <CopyButton text={p.text} />
                </div>
                <div
                  style={{
                    background: "rgba(255,255,255,0.03)",
                    borderRadius: 8,
                    padding: "16px 20px",
                    border: `1px solid ${BORDER}`,
                  }}
                >
                  <p style={{ fontFamily: "'JetBrains Mono', monospace", fontSize: 12, color: GRAY, lineHeight: 1.85, margin: 0 }}>
                    {p.text}
                  </p>
                </div>
              </div>
            ))}
          </div>
        </section>

        {/* TOOLS */}
        <section id="tools" style={{ borderTop: `1px solid ${BORDER}`, paddingBottom: 80 }}>
          <div style={sectionStyle}>
            <Tag color={TEAL}>ESZKÖZÖK</Tag>
            <h2 style={{ ...h2Style, marginTop: 20 }}>
              Ajánlott eszközök
              <br />
              <span style={{ color: TEAL }}>no-code, felhőalapú</span>
            </h2>
            <div style={{ width: 40, height: 2, background: TEAL, margin: "20px 0", borderRadius: 2 }} />

            <div style={{ display: "grid", gap: 12, marginTop: 24 }}>
              {[
                { name: "ChatGPT / Claude", desc: "Fájdalompont-feltérképezés, hook-generálás, forgatókönyv-írás", icon: "🤖" },
                { name: "AnswerThePublic", desc: "Valódi keresési kérdések feltárása bármely iparágban (ingyenes)", icon: "🔍" },
                { name: "Facebook Csoportok", desc: "A célközönséged nyers, szűretlen panaszai — arany a marketinghez", icon: "👥" },
                { name: "Google Trends", desc: "Szezonális trendek és keresési volumen összehasonlítás", icon: "📈" },
                { name: "SparkToro", desc: "Célközönség-kutatás: hol lógnak online, mit olvasnak, kit követnek", icon: "🎯" },
              ].map((tool) => (
                <div
                  key={tool.name}
                  style={{
                    background: CARD,
                    borderRadius: 10,
                    border: `1px solid ${BORDER}`,
                    padding: "18px 22px",
                    display: "flex",
                    alignItems: "center",
                    gap: 16,
                  }}
                >
                  <span style={{ fontSize: 24 }}>{tool.icon}</span>
                  <div>
                    <div style={{ fontSize: 14, fontWeight: 700, color: WHITE, marginBottom: 4 }}>{tool.name}</div>
                    <div style={{ fontSize: 13, color: GRAY, lineHeight: 1.5 }}>{tool.desc}</div>
                  </div>
                </div>
              ))}
            </div>
          </div>
        </section>
      </main>
    </div>
  );
}
