<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Tiendas Referidos Navideños</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Rubik:wght@400;500;700;900&display=swap">
<style>
:root{
  --bg:#FFFFFF; --panel:#F0F0F0; --fg:#000000; --muted:#5b5f66; --line:#e2e2e2;
  --coral:#F48078; --mint:#4FB98C; --yellow:#F4C93E; --ink:#000000; --on-accent:#FFFFFF;
  --row-alt:#f8f8f8;
  --font:'Rubik',system-ui,-apple-system,'Segoe UI',Arial,sans-serif;
}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){
  --bg:#15171b; --panel:#22252b; --fg:#f3f3f3; --muted:#a6abb3; --line:#30343b; --row-alt:#1b1e22; --ink:#f3f3f3; color-scheme:dark}}
:root[data-theme="dark"]{--bg:#15171b; --panel:#22252b; --fg:#f3f3f3; --muted:#a6abb3; --line:#30343b; --row-alt:#1b1e22; --ink:#f3f3f3; color-scheme:dark}
body{margin:0;background:var(--bg);color:var(--fg);font-family:var(--font);font-size:16px;line-height:1.4}
.wrap{max-width:1100px;margin:0 auto;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}

/* HEAD */
.head{position:relative;overflow:hidden;background:var(--coral);color:var(--on-accent)}
.head canvas{position:absolute;inset:0;width:100%;height:100%;pointer-events:none}
.head .wrap{position:relative;padding-block:64px 56px;display:grid;gap:14px}
.eyebrow{font-weight:700;letter-spacing:.14em;text-transform:uppercase;font-size:14px}
.head h1{margin:0;font-weight:900;text-transform:uppercase;font-size:clamp(34px,7vw,64px);line-height:1;text-wrap:balance;max-width:14ch}
.head p{margin:0;font-size:clamp(17px,2.2vw,22px);max-width:40ch}
.ornaments{position:absolute;right:max(16px,4vw);top:0;display:flex;gap:22px;align-items:flex-start}
.orn{display:flex;flex-direction:column;align-items:center}
.orn i{width:2px;background:rgba(255,255,255,.75)}
.orn b{width:10px;height:7px;background:#fff;border-radius:2px 2px 0 0}
.orn span{border-radius:50%;box-shadow:inset -6px -6px 0 rgba(0,0,0,.08)}
@media (max-width:640px){.ornaments{opacity:.45}}

/* FILTROS */
.controls{display:grid;gap:16px;padding-block:28px 8px}
.chips{display:flex;flex-wrap:wrap;gap:10px}
.chip{font:inherit;cursor:pointer;border:2px solid var(--ink);background:transparent;color:var(--fg);border-radius:4px;padding:10px 16px;display:flex;gap:10px;align-items:baseline}
.chip strong{font-weight:700}
.chip small{color:var(--muted);font-size:13px}
.chip[aria-pressed="true"]{background:var(--ink);color:var(--bg)}
.chip[aria-pressed="true"] small{color:inherit;opacity:.75}
.chip:focus-visible,.search:focus-visible{outline:3px solid var(--yellow);outline-offset:2px}
.search{font:inherit;width:100%;max-width:440px;box-sizing:border-box;padding:12px 14px;border:2px solid var(--line);border-radius:4px;background:var(--bg);color:var(--fg)}
.count{color:var(--muted);font-size:14px;margin:0}

/* REGIONES */
.region{margin-top:32px}
.band{background:var(--mint);color:var(--on-accent)}
.band .wrap{padding-block:18px;display:flex;flex-wrap:wrap;gap:6px 24px;align-items:baseline;justify-content:space-between}
.band h2{margin:0;font-weight:900;text-transform:uppercase;font-size:clamp(24px,4vw,34px);letter-spacing:.01em}
.band .meta{display:flex;flex-wrap:wrap;gap:4px 18px;font-size:15px}
.band .meta b{font-weight:700}
.tablebox{overflow-x:auto}
table{width:100%;border-collapse:collapse;font-variant-numeric:tabular-nums;min-width:640px}
th{text-align:left;font-size:12px;letter-spacing:.1em;text-transform:uppercase;color:var(--muted);font-weight:700;padding:14px 12px;border-bottom:2px solid var(--fg)}
td{padding:12px;border-bottom:1px solid var(--line);vertical-align:middle}
tbody tr:nth-child(even){background:var(--row-alt)}
td.t{font-weight:700}
td.n,th.n{text-align:center;width:110px}
.n span{display:inline-grid;place-items:center;min-width:32px;height:32px;border-radius:50%;background:var(--coral);color:#fff;font-weight:700}
.brand{font-size:13px;font-weight:500;padding:3px 8px;border-radius:4px;border:1.5px solid var(--fg);white-space:nowrap}
.brand.is{border-style:dashed}
.state-row td{background:var(--panel);font-weight:700;font-size:13px;letter-spacing:.08em;text-transform:uppercase;padding:8px 12px;color:var(--muted)}
.empty{padding:40px 0;color:var(--muted)}
footer{margin-top:48px;background:var(--panel)}
footer .wrap{padding-block:24px;font-size:14px;color:var(--muted)}

@media print{.controls{display:none!important}td{padding:5px 10px!important}.state-row td{padding:4px 10px!important}.n span{min-width:22px!important;height:22px!important;font-size:12px}.head .wrap{padding-block:36px 32px!important}.region{margin-top:18px!important}footer{margin-top:20px!important}table{min-width:0}.region{break-inside:auto}.band{break-after:avoid}tr{break-inside:avoid}body{-webkit-print-color-adjust:exact;print-color-adjust:exact}}
</style>
</head>
<body>
<header class="head">
  <canvas id="snow" aria-hidden="true"></canvas>
  <div class="ornaments" aria-hidden="true">
    <div class="orn"><i style="height:60px"></i><b></b><span style="width:46px;height:46px;background:#4FB98C"></span></div>
    <div class="orn"><i style="height:110px"></i><b></b><span style="width:62px;height:62px;background:#F4C93E"></span></div>
    <div class="orn"><i style="height:36px"></i><b></b><span style="width:38px;height:38px;background:#FFFFFF"></span></div>
  </div>
  <div class="wrap">
    <div class="eyebrow">Programa de referidos navideños</div>
    <h1>Tiendas participantes</h1>
    <p>Consulta en qué tiendas hay vacantes eventuales del 9 de noviembre al 8 de enero, organizadas por región.</p>
  </div>
</header>

<main>
  <div class="wrap controls">
    <div class="chips" role="group" aria-label="Filtrar por región" id="chips"></div>
    <input class="search" id="q" type="search" placeholder="Busca una tienda, estado o VCD" aria-label="Buscar">
    <p class="count" id="count"></p>
  </div>
  <div id="list"></div>
</main>

<footer><div class="wrap">Listado de consulta. Si detectas un dato incorrecto, avísale a Comunicación Interna.</div></footer>

<script>
const DATA = [{"r": 1, "t": "TM Altaria Ags", "m": "Todomoda", "e": "Aguascalientes", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Gl Coapa 2 Lc", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Paseo Acoxpa", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Perisur 2 Lc", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Portal San Angel", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pq Antenas", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Santa Fe", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Sn Angel Alta", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Sn Jeronimo", "m": "Todomoda", "e": "CDMX", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Gl Saltillo", "m": "Todomoda", "e": "Coahuila", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Se Saltillo", "m": "Todomoda", "e": "Coahuila", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Gl Toluca", "m": "Todomoda", "e": "Edo. de México", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Interlomas", "m": "Todomoda", "e": "Edo. de México", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Metepec", "m": "Todomoda", "e": "Edo. de México", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Pa Interlomas", "m": "Todomoda", "e": "Edo. de México", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Patio Toluca", "m": "Todomoda", "e": "Edo. de México", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Portal Toluca 2", "m": "Todomoda", "e": "Edo. de México", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Se Toluca", "m": "Todomoda", "e": "Edo. de México", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS Cibeles", "m": "Isadora", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS Gl Celaya", "m": "Isadora", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS Pl Mayor Leon Gto", "m": "Isadora", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Altancia León", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM CC Salamanca", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Celaya Cn", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Cibeles", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM La Luciernaga", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Leon Cn 1-5 M", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pl Mayor", "m": "Todomoda", "e": "Guanajuato", "vcd": "César Jiménez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Agora Uruapan", "m": "Todomoda", "e": "Michoacán", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Am Morelia", "m": "Todomoda", "e": "Michoacán", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Mor Cn 1-Mad", "m": "Todomoda", "e": "Michoacán", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Uruapan Cn", "m": "Todomoda", "e": "Michoacán", "vcd": "Daniela Rodríguez", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS Pl Fa Anahuac", "m": "Isadora", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Cumbres Mty", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Gl Mty", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Mty Citadel", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Mty Cn 2", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pa La Fe Mty", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Patio Lincoln", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pl Fiesta Anahuac", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Se Esc Mty", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Sun Mall Mty", "m": "Todomoda", "e": "Nuevo León", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Angelopolis", "m": "Todomoda", "e": "Puebla", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Explanada Puebla", "m": "Todomoda", "e": "Puebla", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Gl Serdan Pue", "m": "Todomoda", "e": "Puebla", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Parque Puebla", "m": "Todomoda", "e": "Puebla", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS Gl Queretaro", "m": "Isadora", "e": "Querétaro", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Paseo Queretaro", "m": "Todomoda", "e": "Querétaro", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Puerta La Victoria", "m": "Todomoda", "e": "Querétaro", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Se Qro", "m": "Todomoda", "e": "Querétaro", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Am Chetumal", "m": "Todomoda", "e": "Quintana Roo", "vcd": "René López", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "IS The Park San Luis", "m": "Isadora", "e": "San Luis Potosí", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Dorado SLP", "m": "Todomoda", "e": "San Luis Potosí", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Se San Luis", "m": "Todomoda", "e": "San Luis Potosí", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Sn Luis Potosi Cn", "m": "Todomoda", "e": "San Luis Potosí", "vcd": "Sara Silva", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM D Rio Reynosa", "m": "Todomoda", "e": "Tamaulipas", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 2}, {"r": 1, "t": "TM Patio Matamoros", "m": "Todomoda", "e": "Tamaulipas", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Rl Reynosa", "m": "Todomoda", "e": "Tamaulipas", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Se Periferico Reynosa", "m": "Todomoda", "e": "Tamaulipas", "vcd": "Eder Zozaya", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Am Verac B Rio", "m": "Todomoda", "e": "Veracruz", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Am Xalapa", "m": "Todomoda", "e": "Veracruz", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pl Cristal Xal", "m": "Todomoda", "e": "Veracruz", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 1, "t": "TM Pl Valle Orizaba", "m": "Todomoda", "e": "Veracruz", "vcd": "Berenice Blas", "vcr": "Alejandra Guerrero", "n": 1}, {"r": 2, "t": "TM Macroplaza Tj", "m": "Todomoda", "e": "Baja California", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Peninsula Tj", "m": "Todomoda", "e": "Baja California", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pl Cachanilla", "m": "Todomoda", "e": "Baja California", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pl Rio Tj", "m": "Todomoda", "e": "Baja California", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Tijuana Cn", "m": "Todomoda", "e": "Baja California", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Delta", "m": "Todomoda", "e": "CDMX", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM El Rosario", "m": "Todomoda", "e": "CDMX", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Oasis Coyoacan", "m": "Todomoda", "e": "CDMX", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 2}, {"r": 2, "t": "TM Patriotismo", "m": "Todomoda", "e": "CDMX", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pl Universidad", "m": "Todomoda", "e": "CDMX", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pq Lindavista 2", "m": "Todomoda", "e": "CDMX", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Tezontle", "m": "Todomoda", "e": "CDMX", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Blv Tuxtla", "m": "Todomoda", "e": "Chiapas", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Tuxtla Fashion Mall", "m": "Todomoda", "e": "Chiapas", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Chihuahua Cn", "m": "Todomoda", "e": "Chihuahua", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Fashion Mall Chihuahua", "m": "Todomoda", "e": "Chihuahua", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Juarez Mall", "m": "Todomoda", "e": "Chihuahua", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Se Juarez", "m": "Todomoda", "e": "Chihuahua", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Se Las Torres Jz", "m": "Todomoda", "e": "Chihuahua", "vcd": "Alma Herrera", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Zentralia Col", "m": "Todomoda", "e": "Colima", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Aragon", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Cosmopol", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Atizapan", "m": "Todomoda", "e": "Edo. de México", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Las Americas", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Luna Parc", "m": "Todomoda", "e": "Edo. de México", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Perinorte", "m": "Todomoda", "e": "Edo. de México", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pq Toreo", "m": "Todomoda", "e": "Edo. de México", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Satelite 2 Lc", "m": "Todomoda", "e": "Edo. de México", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM GP Acapulco", "m": "Todomoda", "e": "Guerrero", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Chilpancingo", "m": "Todomoda", "e": "Guerrero", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Diana Acapulco 2", "m": "Todomoda", "e": "Guerrero", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Patio Acapulco", "m": "Todomoda", "e": "Guerrero", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Explanada Pachuca", "m": "Todomoda", "e": "Hidalgo", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Pachuca", "m": "Todomoda", "e": "Hidalgo", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Patio Pachuca", "m": "Todomoda", "e": "Hidalgo", "vcd": "Alexander Alcántara", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "IS Gt Oblatos", "m": "Isadora", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Fr Tlaquepaque", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM GP Gdl Lc", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gdl Cn 2", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Gdl", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Vallarta", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gn Terraza Bel", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pl Patria", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Tlaquepaque Cn", "m": "Todomoda", "e": "Jalisco", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM L Atrios Ctla", "m": "Todomoda", "e": "Morelos", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Paseo Cuernavaca", "m": "Todomoda", "e": "Morelos", "vcd": "Wendoline Sánchez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Tepic Cn", "m": "Todomoda", "e": "Nayarit", "vcd": "Stephania Gutiérrez", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Gl Sn Juan Rio", "m": "Todomoda", "e": "Querétaro", "vcd": "Jhonatan Flores", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Mall Sonora", "m": "Todomoda", "e": "Sonora", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Nogales Mall", "m": "Todomoda", "e": "Sonora", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 2, "t": "TM Pl Ley Sah", "m": "Todomoda", "e": "Sonora", "vcd": "Lizbeth Oregel", "vcr": "Deni Centeno", "n": 1}, {"r": 3, "t": "IS Acoxpa", "m": "Isadora", "e": "CDMX", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Buenavista", "m": "Isadora", "e": "CDMX", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Cn Santa Fe", "m": "Isadora", "e": "CDMX", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Gl Coapa", "m": "Isadora", "e": "CDMX", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Perisur", "m": "Isadora", "e": "CDMX", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Buenavista", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 2}, {"r": 3, "t": "TM Juarez Cn Hist", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 2}, {"r": 3, "t": "TM Metro Chilpancingo", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Miyana Polanco", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Pl Tepeyac", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Via Vallejo", "m": "Todomoda", "e": "CDMX", "vcd": "Alicia Chávez", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Zona Rosa Lc", "m": "Todomoda", "e": "CDMX", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Gl Campeche", "m": "Todomoda", "e": "Campeche", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Gl Metepec", "m": "Isadora", "e": "Edo. de México", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Pl Satelite", "m": "Isadora", "e": "Edo. de México", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Cd Jn Neza", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alicia Chávez", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Chalco", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alicia Chávez", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Se Ixtapaluca", "m": "Todomoda", "e": "Edo. de México", "vcd": "Alicia Chávez", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Am Morelia", "m": "Isadora", "e": "Michoacán", "vcd": "Yosafat Avila", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS AM Py del Carmen", "m": "Isadora", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "IS Am Cancun", "m": "Isadora", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Am Cancun", "m": "Todomoda", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 2}, {"r": 3, "t": "TM Am Py del Carmen", "m": "Todomoda", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM GP Cancun", "m": "Todomoda", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Outlet Cancun", "m": "Todomoda", "e": "Quintana Roo", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Fr Culiacan", "m": "Todomoda", "e": "Sinaloa", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Paseo Mochis", "m": "Todomoda", "e": "Sinaloa", "vcd": "Patricia Félix", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Se Villahermosa", "m": "Todomoda", "e": "Tabasco", "vcd": "Alicia Chávez", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Altabrisa", "m": "Todomoda", "e": "Yucatán", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Am Merida", "m": "Todomoda", "e": "Yucatán", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Gl Merida", "m": "Todomoda", "e": "Yucatán", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 2}, {"r": 3, "t": "TM La Isla Merida", "m": "Todomoda", "e": "Yucatán", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}, {"r": 3, "t": "TM Merida Cen 2", "m": "Todomoda", "e": "Yucatán", "vcd": "Ruth Miranda", "vcr": "Leonardo Rocha", "n": 1}];
const REG = {};
DATA.forEach(d=>{(REG[d.r] ||= {vcr:d.vcr,rows:[],n:0}); REG[d.r].rows.push(d); REG[d.r].n += d.n;});
const regs = Object.keys(REG).map(Number).sort();
let active = 0;
try{ active = +(localStorage.getItem('reg')||0) || 0; if(!REG[active]) active=0; }catch(e){}
const esc = s => String(s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const norm = s => String(s).normalize('NFD').replace(/[\u0300-\u036f]/g,'').toLowerCase();
const total = DATA.reduce((a,d)=>a+d.n,0);

function chips(){
  const items = [{k:0,label:'Todas',sub:`${DATA.length} tiendas · ${total} eventuales`}]
    .concat(regs.map(r=>({k:r,label:`Región ${r}`,sub:`${REG[r].rows.length} tiendas · ${REG[r].n} eventuales`})));
  document.getElementById('chips').innerHTML = items.map(i=>
    `<button class="chip" type="button" data-k="${i.k}" aria-pressed="${i.k===active}"><strong>${i.label}</strong><small>${i.sub}</small></button>`).join('');
}
function render(){
  const q = norm(document.getElementById('q').value.trim());
  let html='', shown=0, ev=0;
  regs.filter(r=>!active||r===active).forEach(r=>{
    const rows = REG[r].rows.filter(d=>!q || norm([d.t,d.e,d.vcd,d.m].join(' ')).includes(q));
    if(!rows.length) return;
    shown += rows.length; const n = rows.reduce((a,d)=>a+d.n,0); ev += n;
    let body='', last='';
    rows.forEach(d=>{
      if(d.e!==last){ body += `<tr class="state-row"><td colspan="4">${esc(d.e)}</td></tr>`; last=d.e; }
      body += `<tr><td class="t">${esc(d.t)}</td><td><span class="brand ${d.m==='Isadora'?'is':''}">${esc(d.m)}</span></td><td>${esc(d.vcd)}</td><td class="n"><span>${d.n}</span></td></tr>`;
    });
    html += `<section class="region"><div class="band"><div class="wrap"><h2>Región ${r}</h2>
      <div class="meta"><span>VCR <b>${esc(REG[r].vcr)}</b></span><span><b>${rows.length}</b> tiendas</span><span><b>${n}</b> eventuales</span></div></div></div>
      <div class="wrap tablebox"><table><thead><tr><th>Tienda</th><th>Marca</th><th>VCD</th><th class="n">Eventuales</th></tr></thead><tbody>${body}</tbody></table></div></section>`;
  });
  document.getElementById('list').innerHTML = html || `<div class="wrap empty">No encontramos tiendas con esa búsqueda. Revisa la ortografía o elige “Todas”.</div>`;
  document.getElementById('count').textContent = `Mostrando ${shown} tiendas · ${ev} eventuales`;
}
document.getElementById('chips').addEventListener('click',e=>{
  const b=e.target.closest('.chip'); if(!b) return;
  active=+b.dataset.k; try{localStorage.setItem('reg',active)}catch(e){}
  chips(); render();
});
document.getElementById('q').addEventListener('input',render);
chips(); render();

/* nieve */
(function(){
  const c=document.getElementById('snow'), x=c.getContext('2d');
  const still = matchMedia('(prefers-reduced-motion: reduce)').matches;
  let W,H,f=[];
  function size(){W=c.width=c.offsetWidth*devicePixelRatio;H=c.height=c.offsetHeight*devicePixelRatio;
    f=Array.from({length:Math.round(W*H/9000/devicePixelRatio)},()=>({x:Math.random()*W,y:Math.random()*H,r:(Math.random()*2.4+0.8)*devicePixelRatio,s:Math.random()*.5+.2,w:Math.random()*6}));}
  function draw(){x.clearRect(0,0,W,H);x.fillStyle='rgba(255,255,255,.75)';
    f.forEach(p=>{x.beginPath();x.arc(p.x,p.y,p.r,0,7);x.fill();
      if(!still){p.y+=p.s*devicePixelRatio;p.w+=.01;p.x+=Math.sin(p.w)*.3;if(p.y>H){p.y=-4;p.x=Math.random()*W}}});
    if(!still) requestAnimationFrame(draw);}
  size(); addEventListener('resize',()=>{size(); if(still) draw();}); draw();
})();
</script>
</body>
</html>
