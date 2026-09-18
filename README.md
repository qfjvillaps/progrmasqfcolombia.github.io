<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Química Farmacéutica / Farmacia en Colombia — SNIES</title>
<style>
  :root{
    --green:#178a4c;
    --green-light:#e5f5ec;
    --green-dark:#0f6236;
    --blue:#2457c9;
    --blue-light:#e8eefc;
    --blue-dark:#173d94;
    --bg:#f5f6f8;
    --panel-bg:#ffffff;
    --border:#dfe3e8;
    --text:#1c2430;
    --text-muted:#647085;
    --accent:#0d2b4e;
    --shadow:0 1px 2px rgba(16,24,40,.06), 0 1px 3px rgba(16,24,40,.08);
    --radius:12px;
    --font:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    font-family:var(--font);
    background:var(--bg);
    color:var(--text);
    line-height:1.45;
    -webkit-font-smoothing:antialiased;
  }
  .app{max-width:1400px;margin:0 auto;padding:24px 20px 60px;}

  /* ---------- header ---------- */
  header.top{
    background:var(--accent);
    color:#fff;
    border-radius:var(--radius);
    padding:22px 26px;
    display:flex;
    flex-wrap:wrap;
    align-items:center;
    justify-content:space-between;
    gap:16px;
  }
  header.top h1{margin:0;font-size:21px;font-weight:650;letter-spacing:-.01em;}
  header.top p{margin:4px 0 0;font-size:13.5px;color:#c9d4e8;max-width:560px;}
  .legend{display:flex;gap:18px;flex-wrap:wrap;}
  .legend-item{display:flex;align-items:center;gap:7px;font-size:13px;color:#e8edf6;}
  .legend-dot{width:11px;height:11px;border-radius:50%;display:inline-block;border:2px solid rgba(255,255,255,.55);}
  .legend-dot.publica{background:var(--green);}
  .legend-dot.privada{background:var(--blue);}

  /* ---------- layout ---------- */
  .main-grid{display:grid;grid-template-columns:340px 1fr;gap:20px;margin-top:20px;align-items:start;}
  @media (max-width:920px){.main-grid{grid-template-columns:1fr;}}
  .panel{background:var(--panel-bg);border:1px solid var(--border);border-radius:var(--radius);box-shadow:var(--shadow);padding:18px;}
  .panel h2{margin:0 0 12px;font-size:15px;font-weight:650;}

  /* ---------- search ---------- */
  .field-search{position:relative;margin-bottom:14px;}
  .field-search input{
    width:100%;padding:9px 12px 9px 34px;border:1px solid var(--border);border-radius:8px;
    font-size:13.5px;font-family:var(--font);background:#fbfcfd;
  }
  .field-search input:focus{outline:2px solid var(--blue);outline-offset:1px;}
  .field-search svg{position:absolute;left:10px;top:50%;transform:translateY(-50%);width:15px;height:15px;stroke:var(--text-muted);}

  /* ---------- dropdown filters ---------- */
  details.filter-dropdown{border:1px solid var(--border);border-radius:9px;margin-bottom:10px;overflow:hidden;background:#fbfcfd;}
  details.filter-dropdown summary{
    cursor:pointer;padding:10px 12px;font-size:13px;font-weight:650;
    display:flex;justify-content:space-between;align-items:center;list-style:none;
  }
  details.filter-dropdown summary::-webkit-details-marker{display:none;}
  details.filter-dropdown summary::after{content:"▾";color:var(--text-muted);font-size:11px;margin-left:8px;transition:transform .15s;}
  details.filter-dropdown[open] summary::after{transform:rotate(180deg);}
  .summary-badge{font-weight:500;color:var(--text-muted);font-size:11.5px;background:#eef1f4;padding:2px 9px;border-radius:20px;}
  .dropdown-body{padding:2px 12px 10px;border-top:1px solid var(--border);max-height:230px;overflow-y:auto;}
  .quick-toggle-row{display:flex;gap:10px;margin:8px 0 4px;}
  .quick-toggle{background:none;border:none;color:var(--blue-dark);font-size:11.5px;cursor:pointer;padding:0;text-decoration:underline;}

  .check-row{display:flex;align-items:center;justify-content:space-between;gap:8px;padding:5px 2px;border-radius:6px;cursor:pointer;font-size:13.5px;}
  .check-row:hover{background:#eef1f4;}
  .check-row label{display:flex;align-items:center;gap:8px;cursor:pointer;flex:1;}
  .check-row input{accent-color:var(--blue);width:15px;height:15px;cursor:pointer;}
  .check-row .count{color:var(--text-muted);font-size:12px;}
  .dot{width:9px;height:9px;border-radius:50%;display:inline-block;flex-shrink:0;}
  .dot.publica{background:var(--green);}
  .dot.privada{background:var(--blue);}

  .list-header{display:flex;align-items:baseline;justify-content:space-between;margin:14px 0 8px;}
  #programList{max-height:400px;overflow-y:auto;border-top:1px solid var(--border);}
  .list-item{display:flex;gap:10px;align-items:flex-start;padding:9px 4px;border-bottom:1px solid #eef0f3;cursor:pointer;}
  .list-item:hover{background:#f7f9fb;}
  .list-item.active{background:var(--blue-light);}
  .list-item .dot{margin-top:5px;}
  .list-item-title{font-size:13px;font-weight:600;}
  .list-item-sub{font-size:12px;color:var(--text-muted);margin-top:1px;}
  .empty-list{padding:18px 4px;color:var(--text-muted);font-size:13px;}

  /* ---------- map ---------- */
  .panel-map{position:relative;}
  .map-caption{font-size:11.5px;color:var(--text-muted);margin-top:10px;}
  .map-caption strong{color:var(--text);}
  #mapSvg{width:100%;height:auto;display:block;}
  .dept-shape{stroke:#4a5666;stroke-width:1;stroke-linejoin:round;cursor:default;}
  .dept-shape.has-programs{stroke-width:1.6;}
  .dept-label{font-size:10px;fill:#2b3440;font-weight:700;pointer-events:none;paint-order:stroke;stroke:#fff;stroke-width:2.4px;stroke-linejoin:round;}
  .city-label-bg{fill:#ffffff;fill-opacity:.72;}
  .city-label{font-size:10px;fill:#374252;font-style:italic;font-weight:600;pointer-events:none;}
  .side-legend{font-size:9px;fill:#2b3440;}
  .side-legend-title{font-size:9.5px;fill:#2b3440;font-weight:700;}

  .marker{cursor:pointer;}
  .marker-dot{stroke:#fff;stroke-width:2;filter:drop-shadow(0 1px 2px rgba(16,24,40,.4));transition:r .12s ease, stroke-width .12s ease;}
  .marker-dot.publica{fill:var(--green);}
  .marker-dot.privada{fill:var(--blue);}
  .marker:hover .marker-dot,.marker.selected .marker-dot{stroke-width:3;}
  .marker:focus{outline:none;}
  .marker:focus .marker-dot{stroke:#173d94;}

  /* ---------- popup ---------- */
  .popup{
    position:absolute;z-index:60;background:#fff;border:1px solid var(--border);border-radius:10px;
    box-shadow:0 14px 34px rgba(16,24,40,.22);padding:14px 16px 12px;width:260px;
  }
  .popup.hidden{display:none;}
  .popup-close{position:absolute;top:6px;right:8px;border:none;background:none;font-size:16px;line-height:1;cursor:pointer;color:var(--text-muted);padding:4px;}
  .popup-close:hover{color:var(--text);}
  .sector-tag{display:inline-block;font-size:10.5px;font-weight:700;padding:2px 8px;border-radius:20px;margin-bottom:8px;}
  .sector-tag.publica{background:var(--green-light);color:var(--green-dark);}
  .sector-tag.privada{background:var(--blue-light);color:var(--blue-dark);}
  .popup h3{margin:0 0 2px;font-size:14.5px;line-height:1.3;}
  .popup-city{color:var(--text-muted);font-size:12px;margin-bottom:10px;}
  .popup dl{margin:0;display:grid;grid-template-columns:auto 1fr;gap:5px 10px;font-size:12.5px;}
  .popup dt{color:var(--text-muted);}
  .popup dd{margin:0;font-weight:600;text-align:right;}
  .popup-subnote{display:block;font-weight:400;color:var(--text-muted);font-size:10.5px;text-align:right;margin-top:1px;}
  .popup-note{margin-top:10px;padding:8px 9px;background:#fff6e9;border:1px solid #f3d9a8;border-radius:7px;font-size:11px;color:#8a5a12;}

  /* ---------- analysis ---------- */
  .panel-analysis{margin-top:20px;}
  .kpi-row{display:grid;grid-template-columns:repeat(6,1fr);gap:12px;margin-bottom:22px;}
  @media (max-width:920px){.kpi-row{grid-template-columns:repeat(3,1fr);}}
  @media (max-width:560px){.kpi-row{grid-template-columns:repeat(2,1fr);}}
  .kpi-card{background:#fbfcfd;border:1px solid var(--border);border-radius:10px;padding:12px 10px;text-align:center;}
  .kpi-value{font-size:21px;font-weight:700;color:var(--accent);}
  .kpi-label{font-size:11px;color:var(--text-muted);margin-top:2px;}

  .charts-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px;}
  @media (max-width:800px){.charts-grid{grid-template-columns:1fr;}}
  .chart-card{background:var(--panel-bg);border:1px solid var(--border);border-radius:var(--radius);box-shadow:var(--shadow);padding:16px 18px;}
  .chart-card.span2{grid-column:1 / -1;}
  .chart-card h3{margin:0 0 4px;font-size:14px;font-weight:650;}
  .chart-card .chart-sub{font-size:11.5px;color:var(--text-muted);margin-bottom:10px;}
  .chart-label{font-size:10.5px;fill:var(--text-muted);}
  .chart-value{font-size:10.5px;fill:var(--text);font-weight:600;}
  .chart-axis{stroke:var(--border);stroke-width:1;}
  .empty-msg{color:var(--text-muted);font-size:12.5px;padding:10px 0;}

  .notes-card{background:#fbfcfd;border:1px solid var(--border);border-radius:var(--radius);padding:16px 18px;margin-top:18px;}
  .notes-card h3{margin:0 0 8px;font-size:14px;}
  .notes-card ul{margin:0;padding-left:18px;font-size:12.5px;color:var(--text-muted);}
  .notes-card li{margin-bottom:6px;}

  footer{margin-top:26px;font-size:11.5px;color:var(--text-muted);text-align:center;}
  footer p{margin:3px 0;}
</style>
</head>
<body>
<div class="app">

  <header class="top">
    <div>
      <h1>Química Farmacéutica / Farmacia en Colombia</h1>
      <p>Programas activos registrados en el SNIES. Haz clic en un punto del mapa o en un programa de la lista para ver el detalle.</p>
    </div>
    <div class="legend">
      <span class="legend-item"><span class="legend-dot publica"></span>Universidad pública</span>
      <span class="legend-item"><span class="legend-dot privada"></span>Universidad privada</span>
    </div>
  </header>

  <div class="main-grid">

    <!-- ===================== FILTERS + LIST ===================== -->
    <aside class="panel panel-filters">
      <h2>Filtros</h2>

      <div class="field-search">
        <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round"><circle cx="11" cy="11" r="7"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
        <input type="text" id="searchInput" placeholder="Buscar universidad o programa…">
      </div>

      <details class="filter-dropdown" id="sectorDropdown">
        <summary>Tipo de universidad <span class="summary-badge" id="sectorSummary">2/2</span></summary>
        <div class="dropdown-body">
          <div class="check-row"><label><input type="checkbox" id="sectorPublica" class="sector-checkbox" checked><span class="dot publica"></span>Pública</label><span class="count" id="countPublica"></span></div>
          <div class="check-row"><label><input type="checkbox" id="sectorPrivada" class="sector-checkbox" checked><span class="dot privada"></span>Privada</label><span class="count" id="countPrivada"></span></div>
        </div>
      </details>

      <details class="filter-dropdown" id="cityDetails">
        <summary>Ciudad <span class="summary-badge" id="citySummary">7/7</span></summary>
        <div class="dropdown-body">
          <div class="quick-toggle-row">
            <button type="button" class="quick-toggle" id="cityAllBtn">Todas</button>
            <button type="button" class="quick-toggle" id="cityNoneBtn">Ninguna</button>
          </div>
          <div id="cityCheckboxes"></div>
        </div>
      </details>

      <details class="filter-dropdown" id="deptDetails">
        <summary>Departamento <span class="summary-badge" id="deptSummary">6/6</span></summary>
        <div class="dropdown-body">
          <div class="quick-toggle-row">
            <button type="button" class="quick-toggle" id="deptAllBtn">Todos</button>
            <button type="button" class="quick-toggle" id="deptNoneBtn">Ninguno</button>
          </div>
          <div id="deptCheckboxes"></div>
        </div>
      </details>

      <div class="list-header">
        <h2 style="margin:0;">Programas (<span id="listCount">17</span>)</h2>
      </div>
      <div id="programList"></div>
    </aside>

    <!-- ===================== MAP ===================== -->
    <section class="panel panel-map" id="mapPanel">
      <h2>Mapa de universidades por departamento</h2>
      <svg id="mapSvg" viewBox="0 0 613 694" xmlns="http://www.w3.org/2000/svg">
        <g id="departmentsLayer"></g>
        <g id="deptLabelsLayer"></g>
        <g id="sideLegendLayer"></g>
        <g id="cityLabelsLayer"></g>
        <g id="markersLayer"></g>
      </svg>
      <div class="popup hidden" id="popup"></div>
      <p class="map-caption">
        <strong>Mapa por departamentos</strong> (fronteras y nombres reales). Los departamentos con programas registrados se muestran en color más intenso; el resto, atenuados. Todos los puntos de universidad se verificaron uno por uno para caer dentro del límite real de su departamento. Los 7 puntos de <strong>Bogotá</strong> se distribuyen dentro de <strong>Cundinamarca</strong> —el departamento que rodea a Bogotá, D.C.— porque Bogotá, D.C. es el departamento más pequeño del país en área y no alcanza para separarlos con claridad; esto es solo un ajuste visual, los programas siguen registrados administrativamente en Bogotá, D.C. (así aparece en la ficha de cada uno). Base cartográfica: <em>@svg-maps/colombia</em> (basada en el trabajo de MapSVG), licencia CC BY 4.0 — incluida en este archivo, sin conexión a internet.
      </p>
    </section>
  </div>

  <!-- ===================== ANALYSIS ===================== -->
  <section class="panel panel-analysis">
    <h2>Análisis de los datos <span style="font-weight:400;color:var(--text-muted);">(<span id="analysisCount">17</span> de 17 programas según filtros)</span></h2>

    <div class="kpi-row">
      <div class="kpi-card"><div class="kpi-value" id="kpiTotal">17</div><div class="kpi-label">Programas</div></div>
      <div class="kpi-card"><div class="kpi-value" id="kpiInst">16</div><div class="kpi-label">Instituciones</div></div>
      <div class="kpi-card"><div class="kpi-value" id="kpiPub">35%</div><div class="kpi-label">Públicos</div></div>
      <div class="kpi-card"><div class="kpi-value" id="kpiPriv">65%</div><div class="kpi-label">Privados</div></div>
      <div class="kpi-card"><div class="kpi-value" id="kpiCred">172.5</div><div class="kpi-label">Créditos prom.</div></div>
      <div class="kpi-card"><div class="kpi-value" id="kpiSem">9.8</div><div class="kpi-label">Semestres prom.</div></div>
    </div>

    <div class="charts-grid">
      <div class="chart-card">
        <h3>Programas por departamento</h3>
        <div class="chart-sub">Verde = pública · Azul = privada</div>
        <div id="chartDepartamento"></div>
      </div>
      <div class="chart-card">
        <h3>Programas por ciudad</h3>
        <div class="chart-sub">Verde = pública · Azul = privada</div>
        <div id="chartCiudad"></div>
      </div>
      <div class="chart-card">
        <h3>Duración del programa (semestres)</h3>
        <div class="chart-sub">Número de programas por duración</div>
        <div id="chartSemestres"></div>
      </div>
      <div class="chart-card">
        <h3>Nombre del programa</h3>
        <div class="chart-sub">Variantes de nombre bajo las que se registra el mismo programa</div>
        <div id="chartPrograma"></div>
      </div>
      <div class="chart-card span2">
        <h3>Créditos por programa</h3>
        <div class="chart-sub">Ordenado de mayor a menor</div>
        <div id="chartCreditos"></div>
      </div>
      <div class="chart-card span2">
        <h3>Costo de matrícula — universidades privadas (COP/semestre)</h3>
        <div class="chart-sub">Las universidades públicas no se incluyen aquí: su matrícula es diferencial (ver nota abajo) y se muestra como $0 en el mapa, según lo solicitado.</div>
        <div id="chartCosto"></div>
      </div>
    </div>

    <div class="notes-card">
      <h3>Notas sobre los datos</h3>
      <ul>
        <li>Existen 17 programas en total.</li>
        <li>El mismo programa se registra en el SNIES bajo tres nombres distintos: <em>Química Farmacéutica</em> (12 registros), <em>Farmacia</em> (4 registros, todos públicos) y <em>Química y Farmacia</em> (1 registro).</li>
        <li>Siguiendo la instrucción de este tablero, todas las universidades públicas se muestran con <strong>costo $0</strong>, ya que su matrícula real es diferencial (varía según estrato/ingresos) y no corresponde a un valor fijo comparable. Donde el SNIES sí reporta una cifra de referencia (Antioquia, Cartagena, Atlántico), esa cifra aparece como nota informativa dentro del detalle de cada punto.</li>
        <li><strong>UNAB</strong> y <strong>Fundación Universitaria Sanitas</strong> no reportan valor de matrícula en el SNIES.</li>
        <li>La <strong>Universidad Nacional de Colombia</strong> registra el mismo programa (Farmacia) en tres sedes bajo el mismo código de institución padre: Bogotá (con Acreditación de Alta Calidad desde 1998), Medellín y Palmira (registros calificados más recientes).</li>
        <li>La <strong>Universidad El Bosque</strong> tiene una nota de vigencia transitoria (hasta 30/09/2025) asociada al Decreto 1174 de 2023 — visible al hacer clic en su punto en el mapa.</li>
        <li>Los 17 programas se concentran en solo <strong>6 de los 33 departamentos</strong> de Colombia: Bogotá D.C., Antioquia, Valle del Cauca, Atlántico, Bolívar y Santander.</li>
      </ul>
    </div>
  </section>

  <footer>
    <p>Fuente de los datos: SNIES (Sistema Nacional de Información de la Educación Superior), Colombia.</p>
    <p>Mapa base de departamentos: paquete <em>@svg-maps/colombia</em>, basado en el trabajo de MapSVG — licencia Creative Commons Atribución 4.0 Internacional (CC BY 4.0).</p>
    <p>Archivo autocontenido: no depende de internet, servidores ni archivos externos.</p>
  </footer>
</div>

<script>
(function(){
  "use strict";

  /* ============================================================
     1. DATOS
     ============================================================ */
  var COLOR_PUBLIC = "#178a4c";
  var COLOR_PRIVATE = "#2457c9";

  var DEPARTMENTS = [{"id": "ama", "name": "Amazonas", "d": "m 303.16,543.59916 1.41,-0.35 0.82,-0.27 5.34,-1.93 6.54,-2.22 5.06,-1.68 2.87,-0.86 3.41,0.2 2.23,-0.04 0.93,0.48 2.8,1.76 1.81,2.72 3.76,0.43 4.06,-0.11 2.62,-0.02 2.8,2.12 0.76,0.56 1.48,0.68 4.61,-0.38 0.66,-1.18 0.38,-0.89 1.28,-1.33 1.5,0 0.93,0.55 1.02,1.24 0.51,1.04 1.14,0.31 1.1,0.05 1.26,-0.05 1.02,-0.3 1.22,-1.24 2.05,-0.29 1.23,1.48 1.54,1.76 3.67,2.2 1.22,0.07 0.76,-1.46 3.4,-3.61 1.68,-0.13 0.48,1.4 3.07,1.49 0.9,0 1.01,-0.48 1.3,-1.09 -0.13,-2.32 0.29,-0.84 0.74,-1.99 0.69,-1.4 0.49,-0.76 0.84,-0.93 5.51,-5.31 1.08,-0.51 1.13,-0.02 1.12,0.23 2.4,0.65 1.8,0.11 1.53,-1.11 0.8,-1.2 0.56,-0.97 0.38,-0.79 0.52,-1.01 0.46,-0.84 0.74,-0.97 3.44,-2.82 4.09,-4.34 1.61,-1.9 0.5,-1.18 -0.22,-1.64 0.76,-0.62 3.04,0.14 1.89,0.93 0.98,0.75 8.52,5.18 4.11,1.3 1.58,-0.65 2.08,2.2 1.04,1.96 1.69,7.58 1.62,2.64 3.01,-1.22 0.7,-1.33 10.41,3.36 1.61,1.66 0.6,0.94 1.32,1.24 2.75,0.9 1.46,-0.33 -0.72,-1.21 2.46,-1.85 2.02,1.06 0.71,0.92 -1.5,5.54 0.06,4.82 -1.33,2.12 0.06,1.57 1.04,0.9 0.95,0.98 0.34,1.76 -1.08,0.84 -1.42,0.83 -0.27,0.89 0.32,0.98 0.51,0.86 5.07,4.02 1.15,0.09 0.84,-0.36 0.69,-0.77 0.32,-0.95 -0.6,-0.61 -1.19,-0.3 -0.59,-0.66 0.06,-0.84 0.65,-0.88 1.36,-0.88 5.83,-0.39 0.2,1.52 -1.12,3.18 0.29,0.84 1.36,0.23 0.82,-0.3 2.85,-1.32 4.23,-1.02 3.25,2.81 -0.06,0.91 0.78,3.54 6.72,-0.9 -0.14,-3.16 1.01,-2.19 0.44,0.95 0.8,3.72 0.9,4.68 0.47,3.76 -0.51,1.78 -2.54,5.92 -2.88,15.9 -2.95,16.26 -0.56,3.08 -0.75,3.93 -0.39,2.14 -6.5,36.27 -3.66,20.56 -2.53,11.98 -0.56,1.01 0.01,-1.13 -1.32,-1.37 -1.34,-0.91 -0.81,-0.54 -3.39,-2.8 -0.54,-0.89 -0.33,-0.78 -0.34,-1.06 -0.42,-1.27 -0.79,-1.54 -2.17,-2.72 -3.65,-2.95 -0.77,-0.38 -0.85,-0.09 -1.82,0.6 -0.72,0.56 -2.29,1.39 -0.88,0.38 -1.12,0 -3.28,-1.22 -4.8,-2.04 2.14,-3.36 1.84,-2.82 2.54,-3.92 4.89,-7.55 1.44,-2.24 14.21,-22.11 -1.28,-2.34 -0.91,0.13 -3.05,-2.36 -0.59,-1.42 -0.41,-1.6 -3.15,-2.83 -1.66,-0.36 -0.83,0.23 -0.91,0.56 -7.69,-0.75 -0.74,-0.39 -2.77,-3.39 -0.33,-1.76 -8.3,-5.44 -4.84,2.17 -5.14,1.37 -3.58,2 -7.16,-0.56 -2.08,-2.69 -4.45,-1.92 -2.33,0.09 -4.02,-0.48 -0.41,-1.18 0.04,-1.21 -0.41,-0.77 -1.18,0.46 -3.57,2.94 -2.59,3.67 -0.76,2.35 -1.72,0.05 -2.09,-0.39 -3.62,1.57 -6.49,3.73 -2.97,-0.3 -1.16,-0.35 -5.07,-1.7 -5.75,-1.4 -3.84,1.34 -5.41,2.05 -2.77,0.67 -0.85,-2.16 -1.32,-2.2 -1.67,0.07 -1.15,0.36 -2.92,-1.6 -1.27,-1 -0.44,-0.75 -0.68,-3.38 1.26,-0.58 0.97,-1.3 0.8,-2.24 -1.32,-9.09 -1.75,-3.05 -2.65,-1.75 -1.72,1.6 -2.39,1.15 -4.93,-2.34 -3.05,-2.03 -0.7,-0.76 0.84,-3.85 0.42,-0.73 1.23,-1.08 -1.23,-2.36 -1.78,-2.42 -0.94,-1.04 -0.19,-1.29 -0.34,-2.51 -4.03,-3.72 -2.45,-0.22 -1.62,0.44 -3.66,-1.01 -1.11,-2.32 -8.65,-5.56 -5.67,-1.55 -1.04,-0.9 -0.6,-1.07 -1.13,-2.31 0.76,-1.29 0.68,-1.85 -1.75,-1.8 -1.07,-1.15 -0.94,-3.08 -0.79,-3 z", "fill": "#bfe6c8", "labelX": 406.0, "labelY": 602.7, "fontSize": 12.5, "showLabel": true, "area": 15235.6}, {"id": "ant", "name": "Antioquia", "d": "m 291.15,283.37916 -1.19,-0.2 -6.32,1.84 -5.31,0.6 -1.95,0.46 -1.04,1.36 -0.71,1.01 -3.99,2.79 -1.27,-0.58 -1.38,-1.06 -1.35,-1.25 -0.84,-0.35 -4.43,-0.34 -6.45,-1.91 -1.58,-0.51 -1.36,-0.2 -0.06,1.18 0.61,3.82 0.17,3.01 -0.7,0.52 -2.61,-0.26 -1.85,-0.18 -2.31,0.29 -1.12,0.29 -3.06,1.62 -0.84,0.11 -3.51,0.08 -0.59,-0.34 -1.56,-1.45 -0.87,-0.98 -1.93,-2.48 -0.36,-1.02 0.74,-1.64 0.11,-1.26 -0.24,-1.18 -0.63,-1.54 -0.62,-1.14 -0.43,-1.08 -0.18,-0.99 0.18,-0.98 0.63,-1.2 0.21,-3.15 -2.37,-0.47 -0.84,-0.28 -0.74,-0.66 -0.61,-1.65 -0.15,-1.25 -0.05,-1.32 -0.21,-2.85 -0.6,-0.7 -1.88,-1.01 -0.96,-0.14 -9.57,1.69 -1.19,0.37 -0.9,0.11 -4.32,-0.19 -3.39,-4.76 -0.29,-0.96 0.01,-1.09 -0.01,-3.37 -0.28,-1.55 -3.67,-7.77 -0.88,-0.82 -2.1,-1.34 -0.39,-5.42 2.27,-0.76 1.57,0.11 1.48,0.53 1.93,-1.61 0.08,-1.51 -0.51,-1.41 -0.75,-1.72 0.67,-1.01 5.86,-0.22 2.94,0.6 1.4,0.7 0.83,0.23 0.77,-0.42 1.17,-7.02 -0.41,-1.66 -0.56,-1.36 -0.6,-0.91 -2.07,-2.81 -1.55,-0.43 -0.9,-0.46 -2.5,-2 -7.58,-7.72 -0.88,-0.92 -0.81,-0.87 -2.48,-2.81 -1.29,-1.6 -3.06,-0.68 -0.57,-3.8 1.5,-0.45 0.95,-0.59 0.89,-0.96 0.6,-1.53 0.23,-1.46 0.44,-2.18 0.53,-0.75 2.35,-1.66 1.1,-0.34 1.39,-0.41 1.23,-1.93 0.19,0.17 0.06,1.77 -0.17,2.48 -1.39,-0.34 -0.93,-0.5 -0.98,0.63 -0.44,1.9 0.15,2.05 2.14,1.1 2.27,0.18 2.43,-0.59 0.55,-0.68 0.52,-4.28 -0.29,-2.12 -0.59,-4.42 -0.5,-5.93 -0.35,-2.92 -1.98,-2.94 -2.26,-1.62 -2.12,-0.65 -0.01,-1.29 1.8,-2.23 2.75,-0.49 5.94,-1.77 9.95,-8.28 0.24,-1.24 0.7,0.55 0.42,0.73 0.29,0.81 0.08,0.84 0.02,1.5 0.12,1.09 0.22,1.28 0.56,2.02 0.58,1.07 0.59,0.76 0.79,0.74 0.93,0.58 1.2,0.62 1.07,0.42 1.47,0.74 0.61,0.73 0.19,1.05 -0.03,1.77 -0.07,1.35 -0.2,1.37 -0.34,1.08 -0.63,1.08 -0.75,0.87 -1.19,1.18 -0.81,0.57 -1.96,2 -1.03,1.19 -0.99,2.06 -0.47,1.42 -0.31,1.42 -0.36,2.16 -0.14,1.13 -0.09,2.08 -0.47,1.61 -1.57,1.56 -0.98,0.96 -0.78,1.33 -0.38,4.27 -0.02,1.46 0.06,0.93 0.33,2.16 0.34,1.49 0.34,1.15 0.61,1.12 1.56,2.39 3.88,5.04 1.41,0.23 1.23,-0.05 0.91,-0.1 2.82,-0.11 8.05,-0.05 2.01,0.03 2.99,0.15 1.28,-0.32 6.91,-8.57 0.53,-3.06 1.2,-2.04 0.51,-0.73 1.05,-1.02 1.28,-0.23 0.9,0.48 1.29,1.14 0.87,0.28 0.69,-0.62 0.43,-1.96 0.83,-2.31 1.01,-0.35 1.36,-0.45 1.1,-0.52 0.93,-1.28 0.29,-0.82 0.48,-1.17 4.57,-4.35 1.14,-0.3 2.45,0.1 2.17,0.17 2.34,0 1.13,-0.05 1.02,-0.29 0.85,-0.41 0.82,-0.62 0.64,-0.76 0.48,-0.73 1.29,-1.85 1.26,-1.35 2.08,1.77 2.23,1.88 0.8,0.59 1.7,1.12 2.16,1.29 1.11,0.7 0.81,0.62 0.96,1.05 0.37,0.78 0.21,1.01 0.02,0.89 -0.02,3.09 0.19,1.99 0.88,1.08 -0.96,4.56 -2.76,6.89 0,0.97 0.42,0.75 0.61,0.73 3.33,3.42 2.18,-1.69 0.51,-0.81 0.95,-1.95 0.88,-1.15 0.81,-0.53 0.78,0.33 0.51,1.04 0.11,1.44 -0.48,0.8 -0.93,1.1 -0.79,1.49 -0.21,1 -0.27,3.95 0.13,1.21 2.39,7.11 1.46,0.22 1.21,-0.02 1.57,-0.39 4.36,-3.77 1.26,-1.15 1.93,-1.91 2.32,-2.33 2.24,-2.25 -0.22,0.75 -0.21,1.22 0.01,0.85 0.49,4.36 0.53,1.04 0.77,0.93 0.46,1.64 -0.07,1.05 -1.86,1.7 -1.87,0.84 -1.4,0.75 -2.12,2.27 -1.08,1.8 -0.78,1.36 -0.64,0.63 -1.27,1.01 -4.87,3.79 -2.71,1.26 -1.3,0.04 -1.49,1.85 -0.39,1.41 0.33,3.53 1.05,1.73 -0.35,0.86 -3.89,4.33 -0.97,0.72 -1.64,0.7 -0.5,0.57 -0.61,0.82 -1.12,3.44 0,1.72 0.17,5.11 -0.7,0.71 -1.41,5.04 z", "fill": "#cfc3e8", "labelX": 256.7, "labelY": 224.7, "fontSize": 12.5, "showLabel": true, "area": 8737.0}, {"id": "ara", "name": "Arauca", "d": "m 489.73,272.41916 -2.52,-1.54 -6.85,-5.51 -2.48,-2.24 -3.24,-1.43 -7.33,-0.14 -2.12,0.67 -2.18,1.24 -0.78,0.35 -1.1,0.45 -6.04,0.4 -2.51,0 -5.69,-0.18 -2.78,-0.16 -1.59,-0.17 -8.34,-1.82 -1.16,-0.46 -2.29,0.59 -1.33,0.54 -1.07,0.63 -6.81,1.95 -0.83,0.07 -3.11,-0.01 -1.18,-0.93 -5.51,0.3 -8.92,1.87 -1.55,1.09 -0.75,0.66 -2.99,1.8 -0.86,-0.03 -1.67,-0.35 -3.5,-1.58 -3.34,-4.4 -0.37,-1.46 -0.08,-1 0.22,-1.79 3.45,-3.89 4.11,-2.1 1.02,-0.88 0.34,-1.25 0.09,-1.14 2.35,-5.44 1.89,-3.33 0.29,-0.87 0.13,-0.81 0.21,-1.38 0.1,-1.35 0.33,-1.22 0.58,-1.05 1.89,-2.85 2.06,0.95 1.82,-0.02 1.16,-0.66 4.23,-1.78 2.33,-0.59 1.81,0.11 2,0.53 2.67,0.67 1,0.23 5.42,0.04 2.88,1.44 3.35,0.99 6.44,-0.87 0.81,-0.34 1.42,-0.64 2.58,-1.65 0.9,-1.11 1.19,-0.3 1.57,-0.21 4.11,-0.44 6.89,1.64 4.57,1.95 2.29,1.16 1.04,0.79 0.7,0.47 0.83,0.31 1.2,0.27 1.33,-0.3 0.78,-0.63 0.89,-0.54 2.61,-0.35 1.62,0.28 16.26,20.16 12.17,15.16 -1.63,1.32 -1.13,0.57 -2.18,0.76 -1.64,0.13 -2.41,0.03 -2.36,-0.26 -2.56,-0.26 -1.25,0.22 -1.38,0.59 z", "fill": "#fdf1a8", "labelX": 446.8, "labelY": 250.5, "fontSize": 10, "showLabel": true, "area": 3245.2}, {"id": "atl", "name": "Atlántico", "d": "m 267.15,75.139162 0.88,-0.22 7.55,-4.18 0.32,-1.25 0.36,-1.28 4.2,-4.27 2.19,-2.12 0.29,-0.24 -0.03,0.24 0.81,2.01 1.32,0.84 0.97,0.92 0.53,0.89 2.21,4.07 0.11,5.72 -0.07,2.72 -0.22,4.29 -0.38,1.8 -1.9,1.26 -0.89,0.84 -0.74,0.95 -2.24,5.11 -1.73,4.21 -3.15,-2.67 -4.91,-2.97 -5.06,-3.66 -0.34,-1.77 0.31,-1.35 0.23,-1.05 0.08,-1.21 -0.24,-1.36 -0.78,-2.35 1.04,-0.95 -0.37,-1.37 -0.63,0.66 0.08,-1.44 z", "fill": "#f7c9d6", "labelX": 277.8, "labelY": 79.5, "fontSize": 7.5, "showLabel": true, "area": 490.2}, {"id": "dc", "name": "Bogotá, D.C.", "d": "m 297.99,367.15916 1.01,-0.83 1.3,-1.8 1.25,-2.16 0.36,-0.76 0.83,-3.17 -0.11,-2.81 2.32,-3.26 2.07,-0.07 1.05,-0.39 2.2,-5.36 0.2,-1.5 -0.42,-2.63 -0.21,-2.86 1.39,-9.59 4.33,-7.49 1.02,-0.17 2.12,1.12 0.33,1.97 -0.12,6.87 -0.76,1.23 -0.77,0.93 -1,0.97 -0.77,1.22 -0.37,0.76 -0.51,1.2 -0.23,1.04 -0.28,4.09 -0.87,4.32 -1.19,4.83 0.07,2.59 -1.5,-0.07 -1.23,0.26 -1.04,0.78 -5.88,6.41 -0.75,1.3 -0.59,1.49 -0.86,1.9 -0.68,0.75 -0.83,0.17 -0.77,-0.42 z", "fill": "#fbd3a2", "labelX": 310.3, "labelY": 343.5, "fontSize": 7.5, "showLabel": false, "area": 215.7}, {"id": "bol", "name": "Bolívar", "d": "m 327.18,184.94916 -1.1,0.66 -1.57,1.44 -0.63,1.51 -0.21,0.93 0.01,1.39 0.03,1.26 1.21,4.04 0.74,1.55 0.64,3.23 -0.78,6.67 -1.71,2.71 -1.7,3.9 -0.74,6.38 -2.24,2.25 -2.32,2.33 -1.92,1.91 -1.26,1.15 -4.37,3.78 -1.57,0.39 -1.21,0.02 -1.47,-0.22 -2.38,-7.11 -0.14,-1.22 0.27,-3.95 0.21,-0.99 0.78,-1.5 0.93,-1.1 0.49,-0.8 -0.11,-1.44 -0.51,-1.04 -0.78,-0.32 -0.81,0.53 -0.89,1.15 -0.95,1.95 -0.5,0.8 -2.18,1.69 -3.33,-3.41 -0.62,-0.73 -0.41,-0.75 -0.01,-0.97 2.77,-6.88 0.96,-4.56 -0.88,-1.08 -0.19,-1.99 0.02,-3.09 -0.02,-0.9 -0.21,-1.01 -0.38,-0.77 -0.95,-1.05 -0.81,-0.62 -1.11,-0.7 -2.16,-1.29 -1.69,-1.13 -0.8,-0.59 -2.23,-1.88 -2.08,-1.77 1.8,-0.85 0.65,-0.74 0.36,-1.46 0.35,-0.28 1.16,-0.4 1.53,-0.28 1.99,-0.26 0.92,-1.1 1.68,-3.39 1.11,-3.01 -0.59,-0.98 -0.61,-1.9 -0.37,-1.6 0.01,-7.48 1.53,-1.33 -2.21,-4.96 -1.33,-2.11 -1.19,-1.09 -2.37,-1.66 -1.08,-0.61 -0.79,-0.33 -0.85,-0.31 -2.42,-1.53 -1.7,-2.08 -1.39,-2.76 -0.68,-1.6 -0.17,-1.16 0.11,-0.98 0.33,-2.24 -0.05,-1.14 -0.16,-0.95 -0.66,-0.97 -1.02,-1.23 -0.76,-0.84 -10.63,-8.77 -3.15,-2.26 0.08,-0.87 -0.14,-2.98 -0.38,-1.08 -1.82,-0.79 -3.78,-4.67 -2.01,-4.63 -1.73,0.42 -0.7,0.32 0.45,-1.91 1.55,-1.99 0.1,-2.269998 -0.63,-7.53 2.55,-1.2 -0.06,-1.85 -0.72,-2.46 1.15,-1.78 2.77,-2.74 4.98,-2.74 1.1,0.13 0.39,0.62 0.79,2.35 0.23,1.37 -0.07,1.2 -0.23,1.05 -0.31,1.35 0.34,1.76 5.06,3.66 4.91,2.97 3.15,2.67 -1.37,4.519998 0.4,1.3 1.92,0.91 1.52,0.42 2.2,3.09 -0.29,1.61 -1.31,0.78 -1.23,0.55 -0.39,1.09 0.13,2.57 0.11,0.9 1.93,6.36 0.4,0.74 1.02,4.38 -0.46,2.85 -0.06,1.96 2.45,1.08 0.87,-0.1 0.91,-0.13 2.6,1.77 2.81,3.03 4.13,1.7 1.38,-0.02 3.8,1.7 1.76,1.1 3.11,2.79 1.06,1.71 2.25,2.24 5.8,1.9 3.31,0.67 2.1,0.03 -0.26,2.81 0.68,1.44 1.05,0.96 0.58,5.21 -0.25,3.29 1.18,2.39 0.53,0.86 1.03,3.54 0.45,4.05 -0.23,4.58 -1.12,4.87 z m -60.31,-107.549998 -0.72,-0.29 0.17,-1.92 0.83,-0.06 -0.2,0.81 -0.08,1.46 z", "fill": "#bcd9ef", "labelX": 297.1, "labelY": 155.4, "fontSize": 10, "showLabel": true, "area": 3629.7}, {"id": "boy", "name": "Boyacá", "d": "m 379.75,237.26916 2.52,0 2.74,-0.09 0.98,-0.32 1.21,-1.07 0.59,-1.12 0.66,-1.37 4.14,-2.36 0.85,-0.31 1.07,0.1 1.37,0.37 1.15,0.03 0.8,-0.37 0.8,-0.65 2.53,1.89 2.7,0.27 -1.89,2.85 -0.58,1.05 -0.33,1.22 -0.1,1.35 -0.21,1.38 -0.13,0.81 -0.29,0.87 -1.89,3.33 -2.35,5.44 -0.09,1.14 -0.34,1.25 -1.02,0.88 -4.11,2.1 -3.45,3.89 -0.33,0.23 -1.22,1.2 -0.63,1.04 -0.3,1.06 -0.1,1.16 -0.24,5.2 2.07,2.23 -1.16,4.91 -0.57,0.62 -0.68,2.81 4.47,1.92 1.94,3.31 0.05,0.96 -1.82,4.44 -3.31,1.37 -0.77,-0.47 -0.85,0.33 -0.63,0.6 -0.77,1.08 -0.75,1.12 -1.11,1.58 -0.75,0.91 -5.38,3.89 -4.02,0.55 -1.26,-1.42 -2.07,-1.52 -5.2,6.47 -1.12,3.14 0.41,0.83 2.09,1.9 0.44,0.93 -0.14,0.81 -1.17,1.31 -1.25,0.71 -1.4,0.31 -1.06,0.88 -0.72,1.19 -1.34,4.47 -0.25,1.04 0.13,0.83 1.31,2.2 -1.74,2.92 -1.79,0.23 -2.08,-0.35 -0.93,-0.51 -0.57,-0.78 -1.32,-1.68 -2.56,-1.8 -0.97,-0.47 -0.85,-0.29 -1.25,-0.48 -0.99,-0.42 -1.23,-0.77 -2.41,-1.6 -1.38,-1.32 -0.31,-1.18 0.71,-2.72 0.65,-1.04 1.5,-1.6 -0.71,-4.07 -0.8,-1.62 -0.78,-1.41 -1.79,-5.69 -2.85,-3.4 -2.91,-0.75 -3.21,-3.17 -1.71,0.38 -1.99,1.4 -0.56,1.49 -0.07,1.2 -1.8,1.9 -0.85,0.81 -0.77,0.38 -1.42,0.56 -0.97,-0.07 -5.35,-3.99 -2.76,-0.96 -3.49,-4.45 -0.42,-1.53 1.16,-1.33 0.78,-1.04 -0.68,-3.94 -1.08,-1.24 -1.66,1.26 -2.33,1.11 -1.57,-0.26 -1.83,-0.55 -5.02,1.06 -0.74,0.61 -0.02,-0.59 -0.75,-0.82 0.57,-2.94 1.41,-5.04 0.7,-0.71 -0.17,-5.11 0,-1.72 1.12,-3.44 0.61,-0.82 0.5,-0.57 1.39,1.63 2.17,3.51 1.59,2.38 1.42,1.3 1.17,0.34 0.78,-0.34 0.75,-0.41 1.08,-0.33 1.05,0.38 1.9,4.05 3.72,3.45 4.47,2.5 0.69,0.67 0.77,2.03 0.81,0.67 4.91,-1.21 5.41,-0.62 1.31,1.04 1.25,0.83 1,-0.67 0.69,-2.38 0.17,-0.86 0.79,-4.74 2.44,-5.91 1.27,-1.71 4.82,2.54 0.79,0.74 0.4,0.95 0.08,1.12 -0.1,0.9 -0.31,1.12 -1.1,2.07 -0.16,1.02 0.27,1.69 0.62,1.19 0.89,0.69 1.38,0.39 1.24,-0.14 2.3,-1.08 0.7,-0.75 0.17,-0.99 -0.51,-1.43 0.17,-1.22 0.66,-0.73 1.12,-0.55 0.88,-0.23 1.17,-0.13 1.12,0.22 2.59,0.41 3.01,-2.97 7.64,-9.45 1.1,-2.02 0.62,-1.72 -0.11,-2.08 -0.64,-1.19 -0.65,-1.03 -0.29,-1.44 0.03,-4.14 1.21,-0.19 2.37,1.47 0.53,1.18 0.76,2.73 2.16,-0.07 0.96,-0.21 0.79,-0.47 0.67,-0.8 0.47,-0.95 1.91,-5.51 0.25,-1.09 0.07,-1.21 -0.47,-6.04 -0.41,-1.28 z", "fill": "#bfe6c8", "labelX": 347.5, "labelY": 283.7, "fontSize": 10, "showLabel": true, "area": 3238.4}, {"id": "cal", "name": "Caldas", "d": "m 260.77,322.72916 -3.31,-2.86 -1.68,-1.04 -0.85,-0.05 -3.19,-0.17 -4.29,-1.56 -4.6,1.08 -1.46,0.01 -0.89,-0.73 -1.64,-4.43 0.6,-1.41 4.5,-4.18 4.08,-2.31 1.44,-1.67 0.97,-1.89 -3.47,-2.47 -2.81,0.64 -1.59,0.79 -1.09,0.35 -0.7,-0.9 0.26,-4.6 3.06,-1.62 1.12,-0.29 2.31,-0.29 1.85,0.18 2.61,0.26 0.7,-0.52 -0.17,-3.01 -0.61,-3.82 0.06,-1.18 1.36,0.2 1.58,0.51 6.45,1.91 4.43,0.34 0.84,0.35 1.35,1.25 1.38,1.06 1.27,0.58 3.99,-2.79 0.71,-1.01 1.04,-1.36 1.95,-0.46 5.31,-0.6 6.32,-1.84 1.19,0.2 0.75,0.82 0.02,0.59 -0.31,0.54 -0.72,8.91 0.29,1.84 -1.27,3.23 -0.58,1.16 -0.63,1.06 -1.11,1.57 -0.03,-0.03 -0.9,-0.32 -1.61,-0.41 -1.72,-0.11 -2.49,0 -0.93,0.19 -2.91,0.7 -1.1,0.59 -1.26,1 -0.98,1 -0.41,0.72 -0.51,1.19 -0.7,0.45 -3.71,0.38 -1.4,0 -1.33,0.2 -1.15,1.29 -0.29,0.84 -1.76,6.43 0.51,1.14 0.74,0.97 -0.02,0.91 -0.65,0.77 z", "fill": "#cfc3e8", "labelX": 265.4, "labelY": 303.0, "fontSize": 8.5, "showLabel": true, "area": 1093.4}, {"id": "caq", "name": "Caquetá", "d": "m 399.45,492.39916 0.8,0.69 2.77,3.2 2.74,4.78 1.44,4.41 2.59,0.66 3,2.73 3.27,2.07 3.81,2.1 0.91,-0.25 0.39,-0.42 0.22,1.64 -0.5,1.18 -1.61,1.9 -4.09,4.34 -3.44,2.82 -0.74,0.97 -0.46,0.84 -0.52,1.01 -0.38,0.79 -0.56,0.97 -0.8,1.2 -1.53,1.11 -1.8,-0.11 -2.4,-0.65 -1.12,-0.23 -1.13,0.02 -1.08,0.51 -5.51,5.31 -0.84,0.93 -0.49,0.76 -0.69,1.4 -0.74,1.99 -0.29,0.84 0.13,2.32 -1.3,1.09 -1.01,0.48 -0.9,0 -3.07,-1.49 -0.48,-1.4 -1.68,0.13 -3.4,3.61 -0.76,1.46 -1.22,-0.07 -3.67,-2.2 -1.54,-1.76 -1.23,-1.48 -2.05,0.29 -1.22,1.24 -1.02,0.3 -1.26,0.05 -1.1,-0.05 -1.14,-0.31 -0.51,-1.04 -1.02,-1.24 -0.93,-0.55 -1.5,0 -1.28,1.33 -0.38,0.89 -0.66,1.18 -4.61,0.38 -1.48,-0.68 -0.76,-0.56 -2.8,-2.12 -2.62,0.02 -4.06,0.11 -3.76,-0.43 -1.81,-2.72 -2.8,-1.76 -0.93,-0.48 -2.23,0.04 -3.41,-0.2 -3.51,-0.85 -1.48,-0.52 -2.75,-1.49 -1.98,-1.97 -1.43,-1.5 -3.07,-0.85 -3.57,-2.03 -0.79,-1.09 -1.86,-1.44 -4.36,-1.33 -0.67,0.6 0.15,0.83 -0.79,0.73 -4.88,-0.91 -3.24,-1.94 -0.9,-3.22 0.9,-0.73 0.63,-0.67 -1.56,-4.51 -0.66,-1.05 -0.81,-0.61 -4.43,-0.63 -1.25,-0.29 -4.34,-1.82 -1.04,-4.75 0.55,-1.11 0.11,-0.82 -0.52,-1.08 -0.65,-0.63 -3.91,-1.81 -1.15,0.75 -1.25,0.71 -1.16,-0.26 -1.27,-2.62 -0.15,-1.26 0.38,-1.42 -1.63,-4.4 -1.17,-0.9 -1.65,-0.4 -1.17,0.36 -0.81,0.17 -2.21,0.15 -3.44,-0.92 -0.94,-0.95 -0.54,-1.32 -3.81,-2.14 -1.75,0.64 -2.83,0.42 -3.76,-1.36 -2.77,-3.05 -0.47,-0.84 0.14,-1.45 -0.99,-1.25 -4.85,-0.35 -0.58,0.23 -1.86,-2.24 -1.08,-0.58 -2.45,-0.86 -2.41,-1.57 -0.75,-4.24 0.24,-1.28 1.39,-1.36 1.41,-2.55 1.97,-4.16 -0.02,-1.76 0.54,-0.3 4.31,-0.34 1.65,-0.12 1.35,0 1.33,-0.95 7.85,-10.15 4.3,-5.05 3.46,-4.63 0.77,-2.36 6.57,-7.74 1.82,-1.56 1.71,-3.19 0.42,-2.29 0.35,-1.38 0.53,-0.81 1.33,-1.24 1.48,0.39 0.82,0.33 1.21,-0.31 4.37,-3.57 1.86,-2.32 -0.24,-1.31 -0.5,-0.89 -0.79,-1.2 -0.1,-1.54 0.53,-1.17 3.11,-3.89 0.25,-0.31 3.71,0.92 1.66,0.48 0.87,0.36 0.86,0.46 4.06,2.83 0.85,0.62 0.87,0.84 0.5,0.67 0.49,1.15 0.11,0.87 -0.09,0.97 -0.3,1.08 -0.52,1.1 -0.95,1.12 -0.58,0.58 -1.25,1.78 -0.34,1.14 0.62,8.03 0.2,1.04 0.85,2.44 0.7,1.59 0.31,1.07 0.4,2.8 -0.04,1.34 -0.02,1.69 0.06,0.84 0.27,1.17 1.42,2.54 1.35,1.68 1.25,1.46 1.24,0.84 1.91,0.78 1.76,0.37 1.28,0.25 0.99,0.12 1.06,0.09 1.3,0.21 2.52,0.62 2.63,2.59 1.01,1.61 5.07,3.66 1.31,0.24 2.04,-0.24 1.1,-0.19 1.91,-0.73 1.44,-0.46 3.09,-0.9 1.33,-0.19 1.1,0.08 1.36,0.48 -0.06,0.36 -0.06,1.51 0.37,2.15 0.78,1.26 3.2,3.95 1.75,1.48 1.48,1.68 1.48,3.15 0.26,1.21 0.06,1.34 0.67,1.21 0.79,0.84 0.82,0.79 1.43,1.01 1.08,0.69 1.25,0.85 3.67,3.11 0.77,1.31 3.16,1.33 1.49,0.11 0.98,-0.22 6.35,-4.77 0.51,-0.84 -0.47,-0.9 -0.16,-0.97 1.5,-2.22 1.88,-0.9 3.57,-0.68 2.7,0.68 0.87,1.41 3.44,2.26 0.84,0.24 1.57,-0.3 2.52,2.45 4.99,6.62 1.05,2.77 1.83,3.54 0.88,-0.27 0.92,-0.41 3.87,1.35 1.94,1.51 z", "fill": "#fdf1a8", "labelX": 323.0, "labelY": 473.5, "fontSize": 12.5, "showLabel": true, "area": 12270.0}, {"id": "cas", "name": "Casanare", "d": "m 357.62,325.95916 -1.31,-2.2 -0.13,-0.83 0.25,-1.04 1.34,-4.47 0.72,-1.19 1.06,-0.88 1.4,-0.31 1.25,-0.71 1.17,-1.31 0.14,-0.81 -0.44,-0.93 -2.09,-1.9 -0.41,-0.83 1.12,-3.14 5.2,-6.47 2.07,1.52 1.26,1.42 4.02,-0.55 5.38,-3.89 0.75,-0.91 1.11,-1.58 0.75,-1.12 0.77,-1.08 0.63,-0.6 0.85,-0.33 0.77,0.47 3.31,-1.37 1.82,-4.44 -0.05,-0.96 -1.94,-3.31 -4.47,-1.92 0.68,-2.81 0.57,-0.62 1.16,-4.91 -2.07,-2.23 0.24,-5.2 0.1,-1.16 0.3,-1.06 0.63,-1.04 1.22,-1.2 0.33,-0.23 -0.22,1.79 0.08,1 0.37,1.46 3.34,4.4 3.5,1.58 1.67,0.35 0.86,0.03 2.99,-1.8 0.75,-0.66 1.55,-1.09 8.92,-1.87 5.51,-0.3 1.18,0.93 3.11,0.01 0.83,-0.07 6.81,-1.95 1.07,-0.63 1.33,-0.54 2.29,-0.59 1.16,0.46 8.34,1.82 1.59,0.17 2.78,0.16 5.69,0.18 2.51,0 6.04,-0.4 1.1,-0.45 0.78,-0.35 2.18,-1.24 2.12,-0.67 7.33,0.14 3.24,1.43 2.48,2.24 6.85,5.51 2.52,1.54 -0.5,0.35 -1.35,1.63 -0.62,0.94 -1.01,2.14 -0.56,1.74 -1.01,2.72 -4.26,5.6 -1.07,1.2 -2.93,1.87 -1.06,0.34 -2.48,0.6 -0.95,0.17 -2.03,-0.06 -1.11,0.13 -3.85,1.51 -7.47,4.44 -0.87,0.55 -1.15,0.76 -0.43,1.06 0,0.84 -0.08,0.85 -6.52,6 -1.18,0.7 -1.72,0.83 -4.5,7.6 -0.75,0.97 -0.91,0.77 -0.7,0.44 -0.4,0.44 -3.31,2.04 -1.53,0.87 -1.58,0.52 -1.15,0.1 -2.57,0.94 -0.98,0.42 -8.14,3.7 -2.77,2.05 -0.8,0.47 -1.2,0.49 -3.61,1.22 -4.36,2.78 -0.88,0.97 -3.56,2.78 -2.6,1.19 -1.19,-0.1 -0.9,-0.99 -0.86,-0.84 -1.27,-0.42 -3.75,0.44 -3.45,1.3 -1.17,1.54 -0.68,0.62 -1.5,0.91 -3.8,0.55 -4.27,0.47 -5.33,0.47 -0.81,-0.73 -7.1,-7.7 -2.02,-2.77 -0.46,-1.49 -0.43,-1.11 -1.24,-1.73 -1.37,-1.73 z", "fill": "#f7c9d6", "labelX": 423.0, "labelY": 301.9, "fontSize": 10, "showLabel": true, "area": 6164.9}, {"id": "cau", "name": "Cauca", "d": "m 233.26,477.33916 -0.45,1.04 -4.27,1.57 -1.15,0.25 -5.26,-0.04 -1.36,-0.19 -0.92,-0.3 -4.65,-1.93 -1.01,-1.11 -1.08,-2.24 0.51,-3.99 0.26,-0.81 0.41,-0.72 0.45,-0.89 -0.04,-0.83 -0.45,-1.15 -1.58,-3.09 -1.11,-1 -1.78,-0.16 -1.2,0.72 -1.1,1.8 -1.49,1.18 -1.19,0.29 -2.88,0.56 1.11,-1.97 0.89,-7.17 -0.11,-1.09 -0.86,-1.22 -7.79,-4.81 -0.83,0.09 -1.59,0.58 -0.91,0.2 -5.72,0.42 -1.57,0.01 -1.26,-0.16 0.4,-5.5 0.47,-0.72 1.23,-1.27 0.94,-0.47 0.94,-1.4 0.36,-1 -1.08,-0.98 -1.74,-1.54 -3.37,-4.12 -1.81,-3.05 -0.65,-0.92 -0.76,-0.4 -4.38,0.49 -1.92,0.05 -0.85,0 -2.21,-0.3 -1.18,-0.27 -0.85,-0.28 -1.09,-0.59 -1.69,-1.41 -0.51,-0.88 -1.58,-3.45 -1.42,-2.53 -2.39,-3.56 -1.11,-1.41 -0.51,-0.89 -0.42,-0.99 -0.11,-0.75 0.16,-1.65 1.39,1.91 0.26,1.08 1.49,0.74 3.03,-0.39 1.74,-1.68 -0.79,-1.32 -0.68,-4.66 2.76,-4.52 6.1,-7.53 0.76,-0.38 5.36,-8.24 0.38,-1.13 1.4,1.59 1.83,2.64 6.53,4.76 7.38,0.68 0.93,-1.32 2.41,1.15 2.44,2.73 5.5,-2.78 3.7,-2.22 1.85,-0.21 5.01,-2.22 0.94,-1.75 -0.1,-1.63 -0.69,-0.92 0.93,-1.6 1.95,-0.23 3.5,0.65 1.5,0.79 1.04,0.64 1.27,0.72 1.75,0.77 1.47,0.53 1.75,0.23 0.06,0.7 -0.19,1.37 -0.08,1 0.47,0.81 1.15,1.65 1.22,2.14 0.6,1.3 0.56,0.79 2.59,7.63 2.07,4.51 1.1,1.72 0.61,1.07 1.73,4.39 0.45,1.24 0.15,0.87 -3.09,0.8 -0.8,-0.22 -1.98,-1.64 -1.8,-1.16 -1.8,-0.58 -1.33,0.8 -0.84,1.16 -1.23,1.68 -0.77,0.68 -1.04,0.44 -1.21,0.17 -2.02,-0.55 -0.89,-0.08 -0.95,0.52 -4.02,4.54 -0.12,0.82 0.75,2.27 0.4,0.95 0.45,0.92 0.34,1.37 0,1.22 -0.62,0.54 -1.12,0.3 -1.64,-0.1 -1.68,-0.57 -1.23,-0.67 -1.37,-0.62 -1.34,-0.29 -1.79,0.4 -1.2,0.85 -0.04,2.09 0.58,6.4 0.81,0.94 0.93,0.04 1.38,-0.05 1.9,0.83 1.8,2.54 0.23,1.26 -0.15,1.51 -0.18,1.45 0.44,0.97 3.02,2.86 4.32,2.7 0.85,0.3 1.03,-0.05 1.99,-0.46 0.02,1.76 -1.97,4.16 -1.41,2.55 -1.39,1.36 -0.24,1.28 0.75,4.24 2.41,1.57 2.45,0.86 1.08,0.58 z", "fill": "#fbd3a2", "labelX": 200.4, "labelY": 432.1, "fontSize": 10, "showLabel": true, "area": 3909.6}, {"id": "ces", "name": "Cesar", "d": "m 327.18,184.94916 1.12,-4.88 0.23,-4.58 -0.45,-4.05 -1.03,-3.54 -0.52,-0.86 -1.18,-2.39 0.25,-3.29 -0.57,-5.21 -1.05,-0.97 -0.68,-1.43 0.26,-2.81 0.39,-0.67 1.41,-2.03 0.86,-1.54 -0.86,-1.37 -1.25,-1.31 -1.21,-1.07 -2.16,-4.68 -0.35,-1.23 -0.83,-1.39 -1.94,-3.03 -0.54,-0.8 -1.22,-1.09 -1.33,-0.54 -0.87,-0.78 2.61,-3.54 1.16,-0.64 4.39,0.24 5.47,-0.32 -2.25,-6.41 -4.91,-6.87 -4.74,-6.28 1,-3.83 0.38,-1.09 3.89,-6.679998 2.24,-1.23 0.84,-0.28 5.51,-2.08 8.12,-3.9 -0.5,-1.44 -1.55,-1.53 -0.31,-1.13 -0.03,-0.84 0.11,-0.87 0.57,-0.95 0.83,-1.98 -1.48,-1.72 -1.58,-1.72 -0.56,-0.83 -0.19,-1.26 0.28,-0.92 0.77,-1.03 0.71,1.12 0.71,0.73 1.19,0.32 1.05,0.1 3.66,0.06 3.28,-0.02 1.92,-0.09 1.24,0.21 1.43,0.88 6.88,7.39 0.61,1.58 -0.46,2.82 -0.5,1.07 -1.3,0.57 -2.27,2.87 2.28,1.55 1.41,-0.08 1.44,-0.26 0.91,-0.25 1.62,-0.35 1.27,-0.11 2.11,0.2 0.48,0.12 -0.26,3.17 -0.99,9.739998 -0.73,1.43 -0.86,3.33 -0.37,4.03 -0.75,5.68 -3.17,6.6 -1.48,1.99 -5.26,6.35 -4.89,7.58 -0.59,2.26 -0.25,0.39 -0.41,0.84 -0.51,1.29 -0.19,0.82 -0.98,6.7 -0.15,3.12 0.36,2.1 0.09,2.44 -0.59,1.51 -0.65,0.83 -1.38,1.34 -0.57,0.99 -0.31,1.05 -0.33,2.99 1.74,6.83 0.47,1.03 1.15,0.35 1.16,-0.96 0.05,-1.14 -0.06,-0.9 -0.15,-1.34 0.54,-0.75 1.44,-0.11 0.93,0.43 0.44,0.76 0.19,0.92 0.03,1.35 -0.11,1.93 -0.34,1.69 -1.17,0.72 -0.92,0.12 -0.64,0.73 0,0.98 0.6,1.47 1.55,2.15 0.95,2 0.43,1.17 0.97,3.93 -0.24,1.41 -2.51,5.23 -1,1.57 -1.08,1.01 -1.77,0.93 -1.16,0.29 -4.49,0.55 -0.2,-0.52 -1.06,-0.96 -1.75,-0.14 -2.53,-0.17 -0.54,-1.09 0.38,-1.49 0.96,-1.44 0.81,-1.31 0.31,-1.69 -1.41,-4.01 -0.81,-1.79 -1.61,-3.08 z", "fill": "#bcd9ef", "labelX": 338.5, "labelY": 137.0, "fontSize": 10, "showLabel": true, "area": 3202.2}, {"id": "cho", "name": "Chocó", "d": "m 179.67,163.43916 0.81,0.53 1.92,3.47 0.64,2.56 1.8,2.15 0.86,0.56 0.85,0.31 1.47,0.39 1.21,0.99 0.64,0.99 1.53,2.49 4.66,3.63 0.54,2 0.29,1.28 2.51,1.55 2.03,-0.48 -1.24,1.92 -1.39,0.42 -1.1,0.33 -2.36,1.67 -0.53,0.75 -0.44,2.18 -0.23,1.46 -0.61,1.53 -0.88,0.96 -0.96,0.59 -1.49,0.45 0.56,3.8 3.07,0.68 1.28,1.6 2.48,2.81 0.81,0.87 0.88,0.92 7.58,7.72 2.49,2 0.9,0.46 1.55,0.42 2.07,2.81 0.6,0.92 0.56,1.35 0.41,1.67 -1.17,7.02 -0.76,0.42 -0.83,-0.23 -1.41,-0.71 -2.94,-0.6 -5.86,0.22 -0.67,1.01 0.75,1.71 0.52,1.42 -0.09,1.51 -1.93,1.61 -1.48,-0.53 -1.56,-0.11 -2.27,0.76 0.39,5.42 2.1,1.34 0.88,0.82 3.66,7.77 0.29,1.54 0.01,3.38 -0.02,1.09 0.29,0.96 3.39,4.76 4.33,0.19 0.9,-0.11 1.19,-0.37 9.57,-1.69 0.96,0.14 1.88,1.01 0.6,0.7 0.21,2.85 0.05,1.31 0.15,1.25 0.61,1.66 0.74,0.66 0.85,0.29 2.37,0.46 -0.22,3.16 -0.63,1.2 -0.17,0.97 0.17,0.99 0.43,1.08 0.62,1.14 0.63,1.54 0.24,1.18 -0.11,1.26 -0.74,1.64 0.35,1.02 1.94,2.47 0.87,0.98 1.56,1.45 -0.79,0.25 -0.98,0.37 -1.36,0.51 -6.78,3.22 -0.77,0.5 -3.46,3.6 0.26,1.25 3.91,8.54 0.46,0.74 0.73,0.76 0.81,0.52 0.92,0.48 0.68,0.25 -0.09,0.65 -0.26,1.02 -0.54,1.19 -0.78,0.56 -0.96,0.42 -0.85,0.5 -4.62,3.79 -0.58,0.67 -0.46,0.98 -3.01,6.85 -3.09,5.73 -0.52,0.77 -0.22,0.96 -0.08,0.9 0.17,1.82 0.25,1.15 0.25,0.81 0.34,0.79 1,1.19 1.85,1.83 -0.56,1.47 -4.61,3.69 -6.39,2.03 -1.11,0.15 -1.14,-0.07 -0.9,-0.36 -2.94,-1.82 -5.7,-1.9 -4.12,-3.52 -1.33,-0.55 -0.95,0.05 -1.58,0.39 -0.75,-0.6 -0.92,-1.73 0.24,-0.64 -1.96,-0.42 -1.96,0.07 -1.86,-2.99 1.47,-4.14 0.17,-0.27 0.34,-0.89 0.87,-3.1 -0.15,-4.17 -0.21,-2.93 -0.74,-3.98 -0.33,-1.07 -0.23,-1.03 -0.34,-3 -0.43,-5.84 0.04,-2.96 0.72,-1.97 0.24,-1.55 -0.5,-2.38 -1.52,-6.49 -3.46,-1.97 -2.12,-0.6 1.14,-2.69 3.46,-1.64 1.57,0.26 0.96,0.56 1.33,-0.5 3.15,-3.81 0.4,-2.02 -0.17,-1.24 -3.87,-8.2 -2.85,-3.83 -1.91,-2.06 -0.88,-1.14 -0.54,-1.11 0.54,-4.02 2.82,1.78 0.91,-1.72 1.21,-4.52 0.64,-7.25 -2.79,-5.08 -1.47,-0.88 -0.94,-0.1 -8.24,-6.69 0.56,-4.15 -0.14,-0.97 -1.01,-2.27 -4.64,-3.96 -3.97,-3.18 3.39,-10.31 1.31,0.13 1.12,-0.37 0.68,-0.89 0.46,-1.26 -0.35,-1.34 -1.04,-1.79 -0.19,-0.87 -0.01,-1.4 0.02,-1.07 0.61,-1.11 3.3,1.68 1.64,3.14 0.57,1.69 0.42,0.96 0.94,0.54 10.16,-7.25 0.04,-1.01 -1.65,-2.16 2.42,-4.48 0.67,-0.74 3.28,-1.34 0.71,-2.57 -0.7,-3.66 -1.17,-2.37 -1.22,-2.21 -0.93,-0.71 -2.18,-2.15 -0.56,-0.71 -0.23,-2.16 -0.02,-1.12 -0.26,-1.43 -1.27,-2.18 -0.96,-0.88 -1.63,0.03 -0.3,-2.05 0.97,-1.48 0.56,-0.4 2.75,-3.29 0.26,-1.18 z m -1.35,179.4 0.95,0.54 0.83,1.89 1.5,0.46 -0.55,0.5 -6.89,1.22 -1.99,0.55 0.41,-1.49 4.34,-4.07 0.42,-0.11 0.52,0.19 0.46,0.32 z", "fill": "#bfe6c8", "labelX": 197.1, "labelY": 259.8, "fontSize": 10, "showLabel": true, "area": 6333.0}, {"id": "cor", "name": "Córdoba", "d": "m 284.32,183.68916 -1.26,1.35 -1.29,1.85 -0.48,0.73 -0.64,0.76 -0.82,0.62 -0.85,0.41 -1.02,0.29 -1.13,0.05 -2.34,0 -2.17,-0.17 -2.45,-0.1 -1.14,0.3 -4.57,4.35 -0.48,1.17 -0.29,0.82 -0.93,1.28 -1.1,0.52 -1.36,0.45 -1.01,0.35 -0.83,2.31 -0.43,1.96 -0.69,0.62 -0.87,-0.28 -1.29,-1.14 -0.9,-0.48 -1.28,0.23 -1.05,1.02 -0.51,0.73 -1.2,2.04 -0.53,3.06 -6.91,8.57 -1.28,0.32 -2.99,-0.15 -2.01,-0.03 -8.05,0.05 -2.82,0.11 -0.91,0.1 -1.23,0.05 -1.41,-0.23 -3.88,-5.04 -1.56,-2.39 -0.61,-1.12 -0.34,-1.15 -0.34,-1.49 -0.33,-2.16 -0.06,-0.93 0.02,-1.46 0.38,-4.27 0.78,-1.33 0.98,-0.96 1.57,-1.56 0.47,-1.61 0.09,-2.08 0.14,-1.13 0.36,-2.16 0.31,-1.42 0.47,-1.42 0.99,-2.06 1.03,-1.19 1.96,-2 0.81,-0.57 1.19,-1.18 0.75,-0.87 0.63,-1.08 0.34,-1.08 0.2,-1.37 0.07,-1.35 0.03,-1.77 -0.19,-1.05 -0.61,-0.73 -1.47,-0.74 -1.07,-0.42 -1.2,-0.62 -0.93,-0.58 -0.79,-0.74 -0.59,-0.76 -0.58,-1.07 -0.56,-2.02 -0.22,-1.28 -0.12,-1.09 -0.02,-1.5 -0.08,-0.84 -0.29,-0.81 -0.42,-0.73 -0.7,-0.55 0.32,-0.01 0.82,-0.16 1.05,-0.23 2.31,-0.93 2.2,-2.35 3.44,-8.15 0.33,-1.82 2.56,-3.31 0.86,-0.84 0.75,-0.41 6.3,-3.18 4.23,-0.68 3.74,0.72 0.68,1.41 0.68,0.9 0.75,0.82 0.77,0.65 5.31,3.48 3.83,3.99 0.78,0.66 3.13,0.77 0.85,0.35 0.81,0.45 2.43,2.09 1.56,4.25 0.05,1.04 -0.54,2.53 -1.25,-0.5 -1.34,0.13 -1.77,0.25 -3.17,1.2 -0.06,1.16 2.4,6.25 1.18,7.04 1.2,0.35 1.64,-0.55 0.89,-0.13 1.01,0.59 0.16,2.23 0.24,1.71 3.1,-0.83 2.35,-1.62 0.81,-0.8 1.12,-1.22 5.83,2.44 2.98,2.66 0.18,1.58 0.28,1.55 0.93,1.25 -0.36,1.47 -0.65,0.74 z", "fill": "#cfc3e8", "labelX": 250.9, "labelY": 174.8, "fontSize": 10, "showLabel": true, "area": 3516.2}, {"id": "cun", "name": "Cundinamarca", "d": "m 287.56,303.06916 0.03,0.03 1.11,-1.57 0.63,-1.06 0.58,-1.16 1.27,-3.23 -0.29,-1.84 0.72,-8.91 0.31,-0.54 0.74,-0.61 5.02,-1.06 1.83,0.55 1.57,0.26 2.33,-1.11 1.66,-1.26 1.08,1.24 0.68,3.94 -0.78,1.04 -1.16,1.33 0.42,1.53 3.49,4.45 2.76,0.96 5.35,3.99 0.97,0.07 1.42,-0.56 0.77,-0.38 0.85,-0.81 1.8,-1.9 0.07,-1.2 0.56,-1.49 1.99,-1.4 1.71,-0.38 3.21,3.17 2.91,0.75 2.85,3.4 1.79,5.69 0.78,1.41 0.8,1.62 0.71,4.07 -1.5,1.6 -0.65,1.04 -0.71,2.72 0.31,1.18 1.38,1.32 2.41,1.6 1.23,0.77 0.99,0.42 1.25,0.48 0.85,0.29 0.97,0.47 2.56,1.8 1.32,1.68 0.57,0.78 0.93,0.51 2.08,0.35 1.79,-0.23 1.74,-2.92 0,0.82 -0.31,0.9 -0.72,3.86 -2.18,11.92 -3.28,1.71 -6.72,-1.69 -2.1,0.53 -1.03,0.68 -0.89,0.19 -2.06,-0.45 -0.92,-0.77 -0.82,-2.28 -0.2,-0.94 -0.23,-1.44 -0.52,-1.44 -0.8,-0.64 -1.13,-0.58 -5.22,-1.33 -1.3,0.99 -1.47,2.25 -0.6,1.5 0.73,0.97 1.21,0.3 1.77,3.71 0.17,0.92 0,2.06 -1.1,0.56 -0.93,-0.01 -1.73,0.06 -6.67,3.4 -0.78,0.61 -0.86,0.87 -0.89,0.7 -1.77,1.12 -0.98,0.35 -1.06,0.08 -0.07,-2.59 1.19,-4.83 0.87,-4.32 0.28,-4.09 0.23,-1.04 0.51,-1.2 0.37,-0.76 0.77,-1.22 1,-0.97 0.77,-0.93 0.76,-1.23 0.12,-6.87 -0.33,-1.97 -2.12,-1.12 -1.02,0.17 -4.33,7.49 -1.39,9.59 0.21,2.86 0.42,2.63 -0.2,1.5 -2.2,5.36 -1.05,0.39 -2.07,0.07 -2.32,3.26 0.11,2.81 -0.83,3.17 -0.36,0.76 -1.25,2.16 -1.3,1.8 -1.01,0.83 0.11,-0.22 0.45,-1.23 -0.14,-0.95 -1.63,-0.9 -0.6,-0.76 -0.05,-0.26 1.03,-2.57 0.11,-1.25 0.15,-4.73 1.37,-2.79 -0.04,-1.24 -0.42,-0.96 -1.36,-2.05 -0.98,-1.13 -1.15,-0.34 -1.46,0.49 -0.98,1.57 -1.17,0.53 -1.01,-0.11 -8.01,-3.09 -0.82,-0.65 0.67,-1.82 2.89,-5.47 0.72,-2.2 -0.51,-1.15 -0.27,-1.5 -0.17,-1.32 -0.42,-4.47 2.2,-4.78 1.81,-11.55 -0.58,-6.74 z", "fill": "#fdf1a8", "labelX": 319.5, "labelY": 324.4, "fontSize": 10, "showLabel": true, "area": 3121.2}, {"id": "gua", "name": "Guainía", "d": "m 577.71,354.13916 0.65,3.17 0.5,1.99 1.87,5.07 0.79,1.59 0.67,0.75 0.94,0.34 1.45,-0.17 1.24,-0.06 0.85,0.56 2.23,3.12 0.36,1.65 1.35,3.92 0.59,1.09 0.75,0.53 0.88,0.27 1.45,0.56 0.56,2.33 -2.21,3.37 -0.96,0.37 -2.71,2.09 -2.66,2.59 -6.45,6.06 -7.27,6.81 0.39,2.03 2.38,-0.22 5.41,0.95 1.18,0.66 0.67,1.19 2.24,3.45 2.05,1.09 6.61,7.35 1.8,1.44 0.97,0.41 1.58,0.65 1.12,0.84 0.75,2.3 -0.43,0.83 -0.94,0.87 -0.39,0.81 0.22,1.29 0.53,1.48 0.97,2.22 0.6,0.85 1.95,4.34 5.01,13.55 2.69,9.67 1.13,7.19 0.31,1.34 0.68,1.04 0.19,0.21 -0.61,-0.01 -6.08,1.58 -1.75,0.41 -0.37,-0.87 -0.15,-2.97 0,-0.82 0.31,-4.05 0.27,-1.2 0.42,-0.97 0.28,-3.35 -0.59,-4.11 -1.75,-4.69 -1.95,-3.43 -1.88,-2.34 -0.89,-0.66 -1.51,-2.25 -1.82,-3.52 -0.45,-1.24 -0.23,-1.04 -0.59,-1.01 -3.41,-1.22 -3.44,1.47 -2.47,1.63 -0.83,0.58 -3.31,3.26 -0.44,1.5 -0.42,0.71 -3.46,4.12 -1.67,1.42 -2.51,1.19 -1.74,0.41 -1.11,0.11 -1.07,-0.14 -0.95,-0.32 -0.8,-0.6 -1.04,-1.35 -1.24,-2.13 -0.4,-0.77 -0.55,-2.25 -0.67,-1.01 -0.79,-0.49 -2.08,-0.57 -0.91,0 -1.24,1.8 -0.43,0.98 -0.83,2.33 1,3.17 0.88,0.15 1.19,0.22 1.22,1.73 -27.85,-0.08 -11.3,-0.06 -5.65,-0.02 -5.46,0 -1.14,-0.67 -2.43,-0.65 -3.9,-0.97 -6.05,1.59 -3.48,1.54 -2.51,-0.12 -1.37,-1.12 -3.78,-0.92 -1.14,-0.17 -1.28,-0.08 -1.19,-0.41 -1.62,-1.27 -2.07,-1.78 -0.97,-1.37 -0.28,-3.72 0.99,-0.49 0.63,-0.93 -0.51,-2.37 -0.11,-0.23 0.66,-1.34 2.34,-1.72 1.03,-0.58 2.24,-2.67 -1.33,-2.25 -1.85,-0.87 -1.76,1.03 -7.7,1.45 -7.39,0.07 -6.19,-2.91 -1.14,-2.33 -1.21,-2.72 -3.12,-3.87 -2.62,-0.02 -0.88,-1.17 1.92,-1.65 2.16,-1.34 3.04,-1.8 1.3,-0.82 5.37,-3.61 0.83,-1.19 1.97,-0.35 1.93,-0.51 1.04,-0.46 3.08,-4.22 -0.1,-1.27 -0.31,-1.74 0.29,-3.26 2.06,-3.47 1.69,-0.44 1.64,-0.01 1.8,-0.32 -0.27,-3.03 -0.66,-0.96 -0.6,-1.35 1.35,-1.78 3.39,-1.21 1.15,0.68 2.04,0 4.87,-4.28 4.53,-1.77 1.92,-0.32 2.56,-1.25 1.53,-1.5 0.1,-1.01 -0.27,-1.42 0.83,-0.89 3.77,-0.21 2.05,1.06 2.74,-0.37 1.15,-0.98 3.43,-0.49 1.81,0.76 1.09,0.89 0.25,1.38 6.26,-1.23 4.88,-1.04 2.18,0.93 1.95,-1.69 2.21,-2.15 2.57,-0.74 2,0.17 2.94,0.2 2.03,-0.65 0.71,-1.34 0.51,-0.66 5.73,-5.05 0.9,-0.45 7.15,-0.83 5.42,0 3.36,1.65 0.59,0.79 0.09,1.07 0.74,0.63 2,-1.48 1.37,-1.49 0.96,-1.19 0.77,-0.55 3,-1.12 z", "fill": "#f7c9d6", "labelX": 530.1, "labelY": 413.0, "fontSize": 12.5, "showLabel": true, "area": 9792.7}, {"id": "guv", "name": "Guaviare", "d": "m 476.92,435.05916 -1.04,-0.04 -7.48,2.87 -12.49,3.43 -2.17,0.21 -2.31,-0.04 -4.67,-0.38 -5.39,4.19 -0.89,0.43 -1.87,-0.07 -1.25,0.26 -4.03,2.49 -2.78,3.73 -5.08,5.72 -2.85,1.97 -0.69,1.18 -2.49,6.2 0.07,1.07 0.17,1.14 -0.02,2.2 -3.08,4.22 -2.62,2.55 -1,0.12 -1.36,0.32 -1.31,1.01 -0.55,0.83 -0.36,1.25 -0.25,1.12 -3.59,3.38 -5.29,5.05 -0.73,0.81 -0.07,0.12 -0.72,0.02 -1.94,-1.51 -3.87,-1.35 -0.92,0.41 -0.88,0.27 -1.83,-3.54 -1.05,-2.77 -4.99,-6.62 -2.52,-2.45 -1.57,0.3 -0.84,-0.24 -3.44,-2.26 -0.87,-1.41 -2.7,-0.68 -3.57,0.68 -1.88,0.9 -1.5,2.22 0.16,0.97 0.47,0.9 -0.51,0.84 -6.35,4.77 -0.98,0.22 -1.49,-0.11 -3.16,-1.33 -0.77,-1.31 -3.67,-3.11 -1.25,-0.85 -1.08,-0.69 -1.43,-1.01 -0.82,-0.79 -0.79,-0.84 -0.67,-1.21 -0.06,-1.34 -0.26,-1.21 -1.48,-3.15 -1.48,-1.68 -1.75,-1.48 -3.2,-3.95 -0.78,-1.26 -0.37,-2.15 0.06,-1.51 0.06,-0.36 -0.01,-1.21 0.12,-9.84 0.02,-1.32 0.46,-14.08 1.1,-3.68 8.97,1.14 3.08,-0.36 6.05,-1.34 7.68,-2.61 1.64,-2 1.27,-2.82 0.67,-0.61 1.48,-0.66 1.21,-0.31 1.72,0.99 7.84,-1.91 1.23,-1.83 1.91,-1.75 7.01,-3.58 11.04,-1.01 3.54,0.71 8.19,-1.25 2.63,-0.75 5.58,0.31 7.51,-0.11 4.97,-1.12 4.58,-0.03 2,0 2,0.2 0.54,0.38 0.3,2.14 3.72,-0.67 4.55,1.35 2.35,1.27 4.2,0.21 1.13,-1.01 0.42,-1.77 0.63,-0.99 2.67,0.99 2.1,0.94 1.07,0.33 0.69,-0.32 -0.83,1.19 -5.37,3.61 -1.3,0.82 -3.04,1.8 -2.16,1.34 -1.92,1.65 0.88,1.17 2.62,0.02 3.12,3.87 1.21,2.72 1.14,2.33 6.19,2.91 7.39,-0.07 7.7,-1.45 1.76,-1.03 1.85,0.87 1.33,2.25 -2.24,2.67 -1.03,0.58 -2.34,1.72 z", "fill": "#fbd3a2", "labelX": 407.9, "labelY": 447.1, "fontSize": 10, "showLabel": true, "area": 7591.1}, {"id": "hui", "name": "Huila", "d": "m 229.7,456.73916 -1.99,0.46 -1.03,0.05 -0.85,-0.3 -4.32,-2.7 -3.02,-2.86 -0.44,-0.97 0.18,-1.45 0.15,-1.51 -0.23,-1.26 -1.8,-2.54 -1.9,-0.83 -1.38,0.05 -0.93,-0.04 -0.81,-0.94 -0.58,-6.4 0.04,-2.09 1.2,-0.85 1.79,-0.4 1.34,0.29 1.37,0.62 1.23,0.67 1.68,0.57 1.64,0.1 1.12,-0.3 0.62,-0.54 0,-1.22 -0.34,-1.37 -0.45,-0.92 -0.4,-0.95 -0.75,-2.27 0.12,-0.82 4.02,-4.54 0.95,-0.52 0.89,0.08 2.02,0.55 1.21,-0.17 1.04,-0.44 0.77,-0.68 1.23,-1.68 0.84,-1.16 1.33,-0.8 1.8,0.58 1.8,1.16 1.98,1.64 0.8,0.22 3.09,-0.8 -0.15,-0.87 -0.45,-1.24 -1.73,-4.39 -0.61,-1.07 -1.1,-1.72 -2.07,-4.51 -2.59,-7.63 -0.56,-0.79 0.24,0.06 0.82,0.02 1.04,-0.07 2.48,-0.61 1.61,-0.64 2.62,-1.88 0.98,-1 2.23,-2.17 1.1,-0.44 1.61,-0.05 1.36,-0.06 1.23,-0.16 0.81,-0.33 0.22,-0.9 -0.14,-1.36 2.2,-3.76 0.62,-0.79 6.16,-2.58 1.13,-0.36 11.21,-1.69 1.19,0.35 0.45,0.89 -0.23,1.67 -0.57,0.8 -0.83,0.67 -0.51,1.19 0.89,1.01 1.81,0.46 1.24,-0.05 1.15,-0.27 2.75,-2 3.53,-4.24 -0.07,-1.23 -0.36,-0.99 0.29,-0.85 2.24,-3.72 1.6,-2.32 2.99,-3.8 1.02,-1.25 1.25,-1.04 0.98,-0.74 0.32,-0.17 0.05,0.26 0.6,0.76 1.63,0.9 0.14,0.95 -0.45,1.23 -0.11,0.22 -1.62,4.08 -0.46,0.93 -0.62,0.81 -1.03,1.21 -0.49,0.93 -0.7,2.43 -0.68,2.72 0.23,0.87 0.14,0.98 0.11,2.33 -2.28,3.96 -0.73,1 -0.91,1.07 -1.11,0.84 -0.71,0.45 -1.06,0.59 -1.7,1.15 -2.25,1.65 -1.06,0.92 -1.07,2.76 -0.25,0.31 -3.11,3.89 -0.53,1.17 0.1,1.54 0.79,1.2 0.5,0.89 0.24,1.31 -1.86,2.32 -4.37,3.57 -1.21,0.31 -0.82,-0.33 -1.48,-0.39 -1.33,1.24 -0.53,0.81 -0.35,1.38 -0.42,2.29 -1.71,3.19 -1.82,1.56 -6.57,7.74 -0.77,2.36 -3.46,4.63 -4.3,5.05 -7.85,10.15 -1.33,0.95 -1.35,0 -1.65,0.12 -4.31,0.34 z", "fill": "#bcd9ef", "labelX": 254.6, "labelY": 410.0, "fontSize": 8.5, "showLabel": true, "area": 2741.4}, {"id": "lag", "name": "La Guajira", "d": "m 363.4,90.709162 -0.48,-0.12 -2.11,-0.2 -1.27,0.11 -1.62,0.35 -0.91,0.25 -1.44,0.26 -1.41,0.08 -2.28,-1.55 2.27,-2.87 1.3,-0.57 0.5,-1.07 0.46,-2.82 -0.61,-1.58 -6.88,-7.39 -1.43,-0.88 -1.24,-0.21 -1.92,0.09 -3.28,0.02 -3.66,-0.06 -1.05,-0.1 -1.19,-0.32 -0.71,-0.73 -0.71,-1.12 -0.67,-2.57 0.78,-5.6 1.23,-1.8 0.76,-0.69 0.66,-1.07 0.73,-1.27 0.28,-0.87 -0.01,-0.92 1.17,0.07 5.13,-0.17 1.63,-0.24 1.15,-0.26 1.34,-0.41 0.7,-0.45 2.52,-1.78 0.43,-1.15 2.18,-2 4.46,-3.27 10.96,-7.74 1.56,-0.79 8.79,-3.38 1.25,0.14 1.23,-0.03 1.7,-0.54 5.63,-3.26 0.87,-0.56 1.07,-1.09 3.87,-8.01 -0.01,-0.86 -0.28,-3.36 -0.95,-0.6 0.45,-0.82 0.79,-0.35 4.54,-0.35 2.63,0.25 -0.73,1.1 -1.21,1.38 1.06,1.49 0.95,0.15 1.04,-0.39 3.03,-2.01 2.25,-4.3 4.81,-2.22 2.54,-2.31 -0.98,-0.73 -2.03,0.18 -1.33,0.86 0.51,-1.13 1.38,-0.77 1.2,-0.19 4.04,0.43 1.44,0.32 10.43,4.19 1.34,1.02 0.92,0.83 4.37,8.52 0.16,0.97 -0.14,1.11 -0.7,1.32 -1.75,1.38 -2.4,1.38 -2.08,1.38 -1.53,2.23 -0.21,0.51 -3.24,1.68 -2.67,0.72 -6.53,1.68 -3.92,1.4 -1.98,0.89 -8.19,1.44 -4.3,7.14 -5.63,10.25 -4.47,3.57 -1.32,0.05 -5.04,1.2 -0.79,0.49 -2.01,3.79 -3.86,5.66 -2.93,5.24 -4.34,7.5 -1.1,1.51 -2.75,4.58 z", "fill": "#bfe6c8", "labelX": 385.3, "labelY": 48.5, "fontSize": 8.5, "showLabel": true, "area": 2875.3}, {"id": "mag", "name": "Magdalena", "d": "m 323.56,150.93916 -2.1,-0.03 -3.31,-0.67 -5.8,-1.9 -2.25,-2.23 -1.06,-1.72 -3.11,-2.78 -1.76,-1.1 -3.81,-1.7 -1.38,0.01 -4.13,-1.69 -2.81,-3.04 -2.61,-1.77 -0.91,0.13 -0.86,0.1 -2.45,-1.07 0.06,-1.97 0.46,-2.84 -1.01,-4.38 -0.4,-0.74 -1.94,-6.36 -0.11,-0.9 -0.12,-2.57 0.39,-1.09 1.23,-0.55 1.31,-0.79 0.29,-1.61 -2.2,-3.08 -1.52,-0.43 -1.92,-0.9 -0.41,-1.3 1.37,-4.519998 1.73,-4.21 2.24,-5.11 0.74,-0.95 0.89,-0.84 1.9,-1.26 0.38,-1.8 0.22,-4.29 0.07,-2.72 -0.11,-5.72 -2.21,-4.07 -0.53,-0.89 -0.97,-0.92 -1.32,-0.84 -0.81,-2.01 0.03,-0.24 1.08,0.83 13.59,4.68 1.19,0.26 1.04,0.14 1.12,0.03 1.81,0 1.57,-0.15 1.06,-0.21 0.98,-0.3 -0.52,0.65 -0.93,0.35 -1.13,0.16 -2.65,0.22 -1.91,-0.23 -5.21,3.91 -0.65,2.25 0.59,1.68 3.05,-1.23 2.22,1.95 0.31,0.98 2.59,0.02 0.81,-0.56 0.7,-1.16 1.08,-3.35 1.72,-4.33 1.11,-2.06 1.39,-4.24 -0.37,-3.26 0.07,-1.6 0.89,-1.43 1.09,-1.69 1.4,-0.91 4.86,-1.04 1,0.05 1.78,0.68 0.76,0.83 3.47,1.43 3.14,0.8 4.88,0.02 1.69,-0.25 1.51,-0.08 1.55,-0.03 0.82,0.1 0.01,0.92 -0.28,0.87 -0.73,1.27 -0.66,1.07 -0.76,0.69 -1.23,1.8 -0.78,5.6 0.67,2.57 -0.77,1.03 -0.28,0.92 0.19,1.26 0.56,0.83 1.58,1.72 1.48,1.72 -0.83,1.98 -0.57,0.95 -0.11,0.87 0.03,0.84 0.31,1.13 1.55,1.53 0.5,1.44 -8.12,3.9 -5.51,2.08 -0.84,0.28 -2.24,1.23 -3.89,6.679998 -0.38,1.09 -1,3.83 4.74,6.28 4.91,6.87 2.25,6.41 -5.47,0.32 -4.39,-0.24 -1.16,0.64 -2.61,3.54 0.87,0.78 1.33,0.54 1.22,1.09 0.54,0.8 1.94,3.03 0.83,1.39 0.35,1.23 2.16,4.68 1.21,1.07 1.25,1.31 0.86,1.37 -0.86,1.54 -1.41,2.03 z", "fill": "#cfc3e8", "labelX": 308.4, "labelY": 101.4, "fontSize": 10, "showLabel": true, "area": 3259.8}, {"id": "met", "name": "Meta", "d": "m 438.66,319.10916 -0.08,0.37 0.02,21.15 0.02,9.15 0.04,10.54 0.03,25.31 0.03,10.52 0.02,5.6 0.05,0.53 -0.54,-0.38 -2,-0.2 -2,0 -4.58,0.03 -4.97,1.12 -7.51,0.11 -5.58,-0.31 -2.63,0.75 -8.19,1.25 -3.54,-0.71 -11.04,1.01 -7.01,3.58 -1.91,1.75 -1.23,1.83 -7.84,1.91 -1.72,-0.99 -1.21,0.31 -1.48,0.66 -0.67,0.61 -1.27,2.82 -1.64,2 -7.68,2.61 -6.05,1.34 -3.08,0.36 -8.97,-1.14 -1.1,3.68 -0.46,14.08 -0.02,1.32 -0.12,9.84 0.01,1.21 -1.36,-0.48 -1.1,-0.08 -1.33,0.19 -3.09,0.9 -1.44,0.46 -1.91,0.73 -1.1,0.19 -2.04,0.24 -1.31,-0.24 -5.07,-3.66 -1.01,-1.61 -2.63,-2.59 -2.52,-0.62 -1.3,-0.21 -1.06,-0.09 -0.99,-0.12 -1.28,-0.25 -1.76,-0.37 -1.91,-0.78 -1.24,-0.84 -1.25,-1.46 -1.35,-1.68 -1.42,-2.54 -0.27,-1.17 -0.06,-0.84 0.02,-1.69 0.04,-1.34 -0.4,-2.8 -0.31,-1.07 -0.7,-1.59 -0.85,-2.44 -0.2,-1.04 -0.62,-8.03 0.34,-1.14 1.25,-1.78 0.58,-0.58 0.95,-1.12 0.52,-1.1 0.3,-1.08 0.09,-0.97 -0.11,-0.87 -0.49,-1.15 -0.5,-0.67 -0.87,-0.84 -0.85,-0.62 -4.06,-2.83 -0.86,-0.46 -0.87,-0.36 -1.66,-0.48 -3.71,-0.92 1.07,-2.76 1.06,-0.92 2.25,-1.65 1.7,-1.15 1.06,-0.59 0.71,-0.45 1.11,-0.84 0.91,-1.07 0.73,-1 2.28,-3.96 -0.11,-2.33 -0.14,-0.98 -0.23,-0.87 0.68,-2.72 0.7,-2.43 0.49,-0.93 1.03,-1.21 0.62,-0.81 0.46,-0.93 1.62,-4.08 0.11,0.86 0.77,0.42 0.83,-0.17 0.68,-0.75 0.86,-1.9 0.59,-1.49 0.75,-1.3 5.88,-6.41 1.04,-0.78 1.23,-0.26 1.5,0.07 1.06,-0.08 0.98,-0.35 1.77,-1.12 0.89,-0.7 0.86,-0.87 0.78,-0.61 6.67,-3.4 1.73,-0.06 0.93,0.01 1.1,-0.56 0,-2.06 -0.17,-0.92 -1.77,-3.71 -1.21,-0.3 -0.73,-0.97 0.6,-1.5 1.47,-2.25 1.3,-0.99 5.22,1.33 1.13,0.58 0.8,0.64 0.52,1.44 0.23,1.44 0.2,0.94 0.82,2.28 0.92,0.77 2.06,0.45 0.89,-0.19 1.03,-0.68 2.1,-0.53 6.72,1.69 3.28,-1.71 2.18,-11.92 0.72,-3.86 0.31,-0.9 1.37,1.73 1.24,1.73 0.43,1.11 0.46,1.49 2.02,2.77 7.1,7.7 0.81,0.73 5.33,-0.47 4.27,-0.47 3.8,-0.55 1.5,-0.91 0.68,-0.62 1.17,-1.54 3.45,-1.3 3.75,-0.44 1.27,0.42 0.86,0.84 0.9,0.99 1.19,0.1 2.6,-1.19 3.56,-2.78 0.88,-0.97 4.36,-2.78 3.61,-1.22 1.2,-0.49 0.8,-0.47 2.77,-2.05 8.14,-3.7 0.98,-0.42 2.57,-0.94 1.15,-0.1 1.58,-0.52 1.53,-0.87 3.31,-2.04 z", "fill": "#fdf1a8", "labelX": 359.4, "labelY": 387.0, "fontSize": 12.5, "showLabel": true, "area": 11747.2}, {"id": "nar", "name": "Nariño", "d": "m 201.92,466.29916 -0.8,0.12 -1.22,0.27 -0.9,0.36 -3.75,2.2 -0.9,0.53 -1.29,0.81 -1.17,0.84 -0.46,0.71 0.23,7.78 0.22,1.07 0.44,1.07 1.27,3.91 1.35,5.89 -0.07,0.97 -1.45,0.8 -1.23,0.4 -1.16,0.25 -0.64,3.1 0.5,1.49 0.39,1.52 0.26,2.3 0.07,1.35 -0.09,1.2 -4.62,1.01 -1.12,-0.05 -3.82,-1.1 -2.79,-0.89 -1.76,-1.15 -1.2,-5.26 0.2,-1.8 0.11,-1.5 -0.84,-1.38 -1.22,-0.4 -0.83,0.28 -0.92,0.11 -1.21,-0.75 -0.61,-0.5 -1.84,-1.01 -0.92,-0.74 -0.51,-0.89 -0.1,-1.26 0.22,-1.15 -0.91,-1.14 -0.84,-0.33 -3.35,0.71 -1.41,0.8 -1.64,-0.22 -1.21,-0.49 -1.91,-2.02 -2.87,-1.19 -1.35,0.16 -1.56,-0.16 -1.24,-0.47 -3.1,-2.24 -2.26,-1.94 -0.76,-0.48 -1.45,-0.37 -1.09,-0.2 -0.91,-0.36 -0.89,-0.65 -3.62,-3.51 -0.59,-0.83 -0.44,-0.73 -3.03,-0.69 -0.83,0.44 -1.29,-1.82 -1.66,-0.78 -1.02,-0.4 -0.86,-0.56 -5.45,-6.23 -2.02,-4.51 -2.87,-1.34 -0.84,-0.16 -1.52,-0.04 -1.87,-0.55 -0.8,-1.35 3.22,-4.94 3.77,-3 1.47,-0.45 3.45,0.64 1.19,0.62 4.59,1.68 1.39,-0.1 1.56,-4.71 0.15,-1.43 -2.07,-4.13 -0.96,-0.49 -1.43,-1.39 -1.09,-3.72 -0.26,-1.59 1.83,-3.93 2.47,-4.59 0.71,-1.14 0.35,1.58 0.65,-1.3 0.75,-0.48 2.37,-0.37 0.4,-2.5 1.14,-0.17 1.6,1.22 0.85,0.84 0.91,0.83 3.36,-3.33 4.97,1.16 0.9,0.14 5.59,-1.44 1.51,-1.45 0.38,-2.17 0.1,0.75 0.42,0.98 0.51,0.89 1.1,1.41 2.39,3.56 1.42,2.53 1.58,3.45 0.52,0.88 1.69,1.42 1.09,0.59 0.85,0.27 1.18,0.27 2.21,0.3 0.85,0 1.92,-0.05 4.38,-0.5 0.76,0.4 0.66,0.93 1.81,3.05 3.37,4.11 1.75,1.55 1.08,0.98 -0.36,1 -0.94,1.41 -0.93,0.47 -1.24,1.26 -0.47,0.72 -0.4,5.5 1.26,0.16 1.57,-0.01 5.71,-0.42 0.92,-0.19 1.59,-0.58 0.83,-0.1 7.79,4.81 0.86,1.22 0.1,1.1 -0.89,7.16 -1.12,1.97 z m -53.53,-48.7 -0.35,-0.07 -3.33,-3.08 -0.03,-0.56 0.11,-0.66 0.33,-0.6 0.57,-0.75 1.24,-0.31 0.48,-0.08 0.68,0.1 1.13,2.05 0.17,0.39 0.39,2.05 -0.13,0.43 -0.99,0.97 -0.27,0.12 z", "fill": "#f7c9d6", "labelX": 157.1, "labelY": 459.6, "fontSize": 10, "showLabel": true, "area": 4353.2}, {"id": "nsa", "name": "Norte de Santander", "d": "m 398.63,230.10916 -0.8,0.65 -0.8,0.37 -1.15,-0.03 -1.37,-0.37 -1.07,-0.1 -0.85,0.31 -4.14,2.36 -0.66,1.37 -0.59,1.12 -1.21,1.07 -0.98,0.32 -2.74,0.09 -2.52,0 -0.55,0.2 -0.85,0 -0.55,-0.65 0.16,-1.62 -0.05,-1.52 -0.67,-0.63 -2.98,0.83 -0.91,0.62 -8.25,-3.49 -0.24,-6.64 0.4,-4.76 0,-0.95 -0.16,-0.98 -1.1,-2.96 -0.55,-1.09 -3.49,-6.04 -1.01,-0.28 -7.78,-0.03 -0.84,0.45 -0.49,0.8 -0.87,1.45 -2.72,0.23 -5.7,-1.74 -0.81,-0.26 -0.93,-0.78 -0.52,-1.45 -1.63,-1.63 -1.48,-0.72 4.49,-0.55 1.16,-0.29 1.77,-0.93 1.08,-1.01 1,-1.57 2.51,-5.23 0.24,-1.41 -0.97,-3.93 -0.43,-1.17 -0.95,-2 -1.55,-2.15 -0.6,-1.47 0,-0.98 0.64,-0.73 0.92,-0.12 1.17,-0.72 0.34,-1.69 0.11,-1.93 -0.03,-1.35 -0.19,-0.92 -0.44,-0.76 -0.93,-0.43 -1.44,0.11 -0.54,0.75 0.15,1.34 0.06,0.9 -0.05,1.14 -1.16,0.96 -1.15,-0.35 -0.47,-1.03 -1.74,-6.83 0.33,-2.99 0.31,-1.05 0.57,-0.99 1.38,-1.34 0.65,-0.83 0.59,-1.51 -0.09,-2.44 -0.36,-2.1 0.15,-3.12 0.98,-6.7 0.19,-0.82 0.51,-1.29 0.41,-0.84 0.25,-0.39 1.34,0.21 5.1,-0.2 2.32,-1.02 0.91,-1.17 5.5,-3.24 1.19,1.71 0.94,2.48 -0.17,0.95 3.17,2.44 4.36,1.62 1.76,6.76 2.99,11.44 9.95,10.4 0.73,0.16 0.15,0.07 0.56,0.61 0.5,1.35 1.62,7.65 0.48,2.6 -0.15,1.13 -0.71,0.58 -1.79,0.01 -2.9,5.25 -0.57,10.92 0.05,6.54 2.19,3.19 0.72,0.55 0.16,0.04 3.05,0.55 2.53,0.15 4.44,2.65 -0.38,1.48 -0.03,1.11 0.8,2.63 0.51,1.05 0.8,1.44 0.86,1.43 1.09,1.7 z", "fill": "#fbd3a2", "labelX": 366.9, "labelY": 187.5, "fontSize": 10, "showLabel": true, "area": 3058.9}, {"id": "put", "name": "Putumayo", "d": "m 233.26,477.33916 0.58,-0.23 4.85,0.35 0.99,1.25 -0.14,1.45 0.47,0.84 2.77,3.05 3.76,1.36 2.83,-0.42 1.75,-0.64 3.81,2.14 0.54,1.32 0.94,0.95 3.44,0.92 2.21,-0.15 0.81,-0.17 1.17,-0.36 1.65,0.4 1.17,0.9 1.63,4.4 -0.38,1.42 0.15,1.26 1.27,2.62 1.16,0.26 1.25,-0.71 1.15,-0.75 3.91,1.81 0.65,0.63 0.52,1.08 -0.11,0.82 -0.55,1.11 1.04,4.75 4.34,1.82 1.25,0.29 4.43,0.63 0.81,0.61 0.66,1.05 1.56,4.51 -0.63,0.67 -0.9,0.73 0.9,3.22 3.24,1.94 4.88,0.91 0.79,-0.73 -0.15,-0.83 0.67,-0.6 4.36,1.33 1.86,1.44 0.79,1.09 3.57,2.03 3.07,0.85 1.43,1.5 1.98,1.97 2.75,1.49 1.48,0.52 3.51,0.85 -2.87,0.86 -5.06,1.68 -6.54,2.22 -5.34,1.93 -0.82,0.27 -1.41,0.35 -0.24,-0.39 -0.73,-1.01 -6.72,-5.14 -2.09,-1.4 -1.04,0.94 -3.13,-1.84 -0.29,-1.15 -0.05,-0.9 -0.17,-0.9 -0.51,-1.17 -0.65,-1.04 -0.95,-1.14 -0.81,-0.31 -0.85,0.22 -1.18,0.81 -0.78,0.29 -3.21,-1.37 -0.93,-1.16 -2.5,-1.95 -4.77,-3.18 -2.8,-0.35 -0.48,1.29 -0.38,1.13 -1.37,1.09 -1.1,-0.12 -0.59,-0.71 -1.05,-0.57 -1,-0.41 -2.03,-0.26 -1.46,-0.51 -3.48,-2.11 -2.33,-1.63 -4.89,-0.46 -1.38,0.31 -1.37,-0.46 -6.26,-4.77 -2.78,-3.81 -1.84,-2.61 -0.63,-0.72 -4.33,-1.36 -4.03,-1.01 -6.51,0.13 -0.28,4.94 -1.69,1.01 -3.97,1.14 -0.89,-0.06 -0.75,-0.42 -1.12,-1.14 -4.31,-1 -0.43,0.82 -1.78,0.58 -1.7,0.31 -2.27,0.08 -6.95,-2.73 -1.83,-2.19 0.09,-1.19 -0.07,-1.35 -0.26,-2.3 -0.39,-1.52 -0.5,-1.49 0.63,-3.1 1.16,-0.25 1.22,-0.4 1.46,-0.8 0.07,-0.96 -1.35,-5.9 -1.27,-3.91 -0.43,-1.07 -0.22,-1.07 -0.24,-7.78 0.47,-0.7 1.17,-0.84 1.29,-0.81 0.91,-0.53 3.75,-2.2 0.91,-0.36 1.22,-0.28 0.8,-0.12 2.88,-0.56 1.19,-0.29 1.49,-1.18 1.1,-1.8 1.2,-0.72 1.78,0.16 1.11,1 1.58,3.09 0.45,1.15 0.04,0.83 -0.45,0.89 -0.41,0.72 -0.26,0.81 -0.51,3.99 1.08,2.24 1.01,1.11 4.65,1.93 0.92,0.3 1.36,0.19 5.26,0.04 1.15,-0.25 4.27,-1.57 z", "fill": "#bcd9ef", "labelX": 257.8, "labelY": 502.7, "fontSize": 10, "showLabel": true, "area": 3448.7}, {"id": "qui", "name": "Quindío", "d": "m 248.16,327.66916 0.6,-0.28 4.3,0.31 2.69,0.41 1.23,0.33 1.13,-0.04 2.6,-1.49 0.29,0.55 -3.27,4.79 -2.84,3.41 -1.24,1.59 -0.47,0.92 0.09,1.94 -0.1,1.64 -0.31,0.84 -0.35,0.79 -0.39,0.73 -0.51,0.65 -1.03,1.2 -2.49,3.73 -0.42,2.12 0.05,1.1 -0.92,-0.65 -0.75,-1.33 -0.62,-2.08 -0.76,-2.69 -2.88,-12.71 -0.29,-1.41 0.1,-0.95 0.66,-0.59 2.07,0.18 1.98,-0.04 1.86,-0.38 0.48,-0.8 z", "fill": "#bfe6c8", "labelX": 251.3, "labelY": 339.9, "fontSize": 7.5, "showLabel": false, "area": 227.0}, {"id": "ris", "name": "Risaralda", "d": "m 260.71,326.90916 -2.6,1.49 -1.13,0.04 -1.23,-0.33 -2.69,-0.41 -4.3,-0.31 -0.6,0.28 -2.48,-1.15 -5.39,-1.35 -3.17,-4.57 -3.27,-3.18 -1.47,-1.22 -0.87,-0.31 -1.78,0.31 -0.67,-0.26 -0.92,-0.48 -0.81,-0.52 -0.73,-0.77 -0.46,-0.74 -3.91,-8.54 -0.26,-1.25 3.46,-3.61 0.76,-0.5 6.78,-3.22 1.36,-0.51 0.99,-0.37 0.79,-0.25 0.59,0.34 3.51,-0.08 0.84,-0.11 -0.26,4.6 0.7,0.9 1.09,-0.35 1.59,-0.79 2.81,-0.64 3.47,2.47 -0.97,1.89 -1.44,1.67 -4.08,2.31 -4.5,4.18 -0.6,1.41 1.64,4.43 0.89,0.73 1.46,-0.01 4.6,-1.08 4.29,1.56 3.19,0.17 0.85,0.05 1.68,1.04 3.31,2.86 -1.6,2.1 0.17,0.81 z", "fill": "#cfc3e8", "labelX": 239.8, "labelY": 310.4, "fontSize": 7.5, "showLabel": false, "area": 570.0}, {"id": "sap", "name": "San Andrés y Providencia", "d": "m 0.54,4.489162 -0.29,-0.26 0,-2.05 0.26,-0.83 0.38,-0.64 0.51,-0.42 0.45,0.19 -0.4,2.25 -0.47,1.04 -0.32,0.69 z", "fill": "#fdf1a8", "labelX": 1.1, "labelY": 2.4, "fontSize": 7.5, "showLabel": false, "area": 4.0}, {"id": "san", "name": "Santander", "d": "m 321.38,220.60916 0.74,-6.38 1.7,-3.89 1.71,-2.71 0.78,-6.67 -0.64,-3.23 -0.74,-1.55 -1.21,-4.04 -0.03,-1.26 -0.02,-1.39 0.21,-0.93 0.63,-1.51 1.57,-1.44 1.1,-0.66 0.55,0.99 1.61,3.08 0.81,1.79 1.41,4.01 -0.31,1.69 -0.81,1.31 -0.96,1.44 -0.38,1.49 0.54,1.09 2.53,0.17 1.75,0.14 1.06,0.96 0.2,0.52 1.48,0.72 1.63,1.63 0.52,1.45 0.93,0.78 0.81,0.26 5.7,1.74 2.72,-0.23 0.87,-1.45 0.49,-0.8 0.84,-0.45 7.78,0.03 1.01,0.28 3.49,6.04 0.55,1.09 1.1,2.96 0.16,0.98 0,0.95 -0.4,4.76 0.24,6.64 8.25,3.49 0.91,-0.62 2.98,-0.83 0.67,0.63 0.05,1.52 -0.16,1.62 0.55,0.65 0.85,0 0.55,-0.2 0.31,0.68 0.41,1.28 0.47,6.04 -0.07,1.21 -0.25,1.09 -1.91,5.51 -0.47,0.95 -0.67,0.8 -0.79,0.47 -0.96,0.21 -2.16,0.07 -0.76,-2.73 -0.53,-1.18 -2.37,-1.47 -1.21,0.19 -0.03,4.14 0.29,1.44 0.65,1.03 0.64,1.19 0.11,2.08 -0.62,1.72 -1.1,2.02 -7.64,9.45 -3.01,2.97 -2.59,-0.41 -1.12,-0.22 -1.17,0.13 -0.88,0.23 -1.12,0.55 -0.66,0.73 -0.17,1.22 0.51,1.43 -0.17,0.99 -0.7,0.75 -2.3,1.08 -1.24,0.14 -1.38,-0.39 -0.89,-0.69 -0.62,-1.19 -0.27,-1.69 0.16,-1.02 1.1,-2.07 0.31,-1.12 0.1,-0.9 -0.08,-1.12 -0.4,-0.95 -0.79,-0.74 -4.82,-2.54 -1.27,1.71 -2.44,5.91 -0.79,4.74 -0.17,0.86 -0.69,2.38 -1,0.67 -1.25,-0.83 -1.31,-1.04 -5.41,0.62 -4.91,1.21 -0.81,-0.67 -0.77,-2.03 -0.69,-0.67 -4.47,-2.5 -3.72,-3.45 -1.9,-4.05 -1.05,-0.38 -1.08,0.33 -0.75,0.41 -0.78,0.34 -1.17,-0.34 -1.42,-1.3 -1.59,-2.38 -2.17,-3.51 -1.39,-1.63 1.64,-0.7 0.97,-0.72 3.89,-4.33 0.35,-0.86 -1.05,-1.73 -0.33,-3.53 0.39,-1.41 1.49,-1.85 1.3,-0.04 2.71,-1.26 4.87,-3.79 1.27,-1.01 0.64,-0.63 0.78,-1.36 1.08,-1.8 2.12,-2.27 1.4,-0.75 1.87,-0.84 1.86,-1.7 0.07,-1.05 -0.46,-1.64 -0.77,-0.93 -0.53,-1.04 -0.49,-4.36 -0.01,-0.85 0.21,-1.22 z", "fill": "#f7c9d6", "labelX": 338.4, "labelY": 234.9, "fontSize": 10, "showLabel": true, "area": 4224.8}, {"id": "suc", "name": "Sucre", "d": "m 247.32,132.49916 1.54,0.41 1.28,-0.6 0.92,-0.93 0.59,-0.99 0.91,-2.1 0.29,-1.01 0.22,-1.5 0.02,-0.96 -0.26,-1.18 -0.41,-1.28 -1.05,-1.39 -1.4,-2.55 1.06,-2.67 1.61,-5.52 0.24,-0.92 0.42,-2.75 0,-1.09 -0.1,-0.7 0.7,-0.32 1.73,-0.41 2.01,4.63 3.77,4.67 1.82,0.78 0.39,1.08 0.14,2.98 -0.08,0.87 3.14,2.26 10.64,8.77 0.75,0.84 1.02,1.23 0.67,0.97 0.16,0.94 0.04,1.15 -0.33,2.23 -0.11,0.98 0.17,1.16 0.67,1.61 1.4,2.76 1.69,2.07 2.42,1.54 0.85,0.31 0.79,0.33 1.07,0.61 2.37,1.66 1.19,1.09 1.33,2.11 2.21,4.96 -1.52,1.33 -0.01,7.48 0.36,1.6 0.62,1.9 0.59,0.98 -1.11,3.01 -1.69,3.39 -0.91,1.1 -1.99,0.26 -1.53,0.27 -1.15,0.41 -0.36,0.27 -0.93,-1.25 -0.28,-1.55 -0.18,-1.58 -2.98,-2.66 -5.83,-2.44 -1.12,1.22 -0.81,0.8 -2.35,1.62 -3.1,0.83 -0.24,-1.71 -0.16,-2.23 -1.01,-0.59 -0.89,0.13 -1.64,0.55 -1.2,-0.35 -1.18,-7.04 -2.4,-6.25 0.06,-1.16 3.17,-1.2 1.77,-0.25 1.34,-0.13 1.25,0.5 0.54,-2.53 -0.05,-1.04 -1.56,-4.25 -2.43,-2.09 -0.81,-0.45 -0.85,-0.35 -3.13,-0.77 -0.78,-0.66 -3.83,-3.99 -5.31,-3.48 -0.77,-0.65 -0.75,-0.82 -0.68,-0.9 z", "fill": "#fbd3a2", "labelX": 271.6, "labelY": 142.3, "fontSize": 8.5, "showLabel": true, "area": 1570.5}, {"id": "tol", "name": "Tolima", "d": "m 247.72,352.90916 -0.05,-1.1 0.42,-2.12 2.49,-3.73 1.03,-1.2 0.51,-0.65 0.39,-0.73 0.35,-0.79 0.31,-0.84 0.1,-1.64 -0.09,-1.94 0.47,-0.92 1.24,-1.59 2.84,-3.41 3.27,-4.79 -0.29,-0.55 -1.37,-1.27 -0.17,-0.81 1.6,-2.1 2.21,-1.73 0.65,-0.77 0.02,-0.91 -0.74,-0.97 -0.51,-1.14 1.76,-6.43 0.29,-0.84 1.15,-1.29 1.33,-0.2 1.4,0 3.71,-0.38 0.7,-0.45 0.51,-1.19 0.41,-0.72 0.98,-1 1.26,-1 1.1,-0.59 2.91,-0.7 0.93,-0.19 2.49,0 1.72,0.11 1.61,0.41 0.9,0.32 0.17,0.45 0.58,6.74 -1.81,11.55 -2.2,4.78 0.42,4.47 0.17,1.32 0.27,1.5 0.51,1.15 -0.72,2.2 -2.89,5.47 -0.67,1.82 0.82,0.65 8.01,3.09 1.01,0.11 1.17,-0.53 0.98,-1.57 1.46,-0.49 1.15,0.34 0.98,1.13 1.36,2.05 0.42,0.96 0.04,1.24 -1.37,2.79 -0.15,4.73 -0.11,1.25 -1.03,2.57 -0.32,0.17 -0.98,0.74 -1.25,1.04 -1.02,1.25 -2.99,3.8 -1.6,2.32 -2.24,3.72 -0.29,0.85 0.36,0.99 0.07,1.23 -3.53,4.24 -2.75,2 -1.15,0.27 -1.24,0.05 -1.81,-0.46 -0.89,-1.01 0.51,-1.19 0.83,-0.67 0.57,-0.8 0.23,-1.67 -0.45,-0.89 -1.19,-0.35 -11.21,1.69 -1.13,0.36 -6.16,2.58 -0.62,0.79 -2.2,3.76 0.14,1.36 -0.22,0.9 -0.81,0.33 -1.23,0.16 -1.36,0.06 -1.61,0.05 -1.1,0.44 -2.23,2.17 -0.98,1 -2.62,1.88 -1.61,0.64 -2.48,0.61 -1.04,0.07 -0.82,-0.02 -0.24,-0.06 -0.6,-1.3 -1.22,-2.14 -1.15,-1.65 -0.47,-0.81 0.08,-1 0.19,-1.37 -0.06,-0.7 0.5,-0.4 3.17,-10.68 2.26,-8.81 0.92,-5.04 0.31,-0.86 1.12,-1.99 1.13,-1.68 0.93,-1.04 0.83,-0.18 0.77,0.35 0.78,0.31 2.53,-2.03 0.23,-1.2 0.08,-1.63 z", "fill": "#bcd9ef", "labelX": 265.4, "labelY": 349.8, "fontSize": 10, "showLabel": true, "area": 3159.5}, {"id": "vac", "name": "Valle del Cauca", "d": "m 232.24,388.26916 -1.75,-0.23 -1.47,-0.53 -1.75,-0.77 -1.27,-0.72 -1.04,-0.64 -1.5,-0.79 -3.5,-0.65 -1.95,0.23 -0.93,1.6 0.69,0.92 0.1,1.63 -0.94,1.75 -5.01,2.22 -1.85,0.21 -3.7,2.22 -5.5,2.78 -2.44,-2.73 -2.41,-1.15 -0.93,1.32 -7.38,-0.68 -6.53,-4.76 -1.83,-2.64 -1.4,-1.59 -0.96,-0.53 -1.5,-1.19 0.74,-1.12 3.55,-2.26 4.94,-6.31 1.34,-0.36 2.91,-3.72 0.52,-1.77 0.11,-2.45 3.83,-6.14 -2.07,0.48 -1.22,0.5 -1.94,1.31 -1.19,0.78 -2,0.19 -1.17,-0.05 -0.88,-0.48 -0.45,-2.63 0.49,-1.43 1.06,-0.65 1.88,-0.22 1.12,-3.62 -0.96,-0.69 -2.06,-0.76 -1.41,1.32 -0.73,0.92 -0.68,2.24 -0.63,1.45 -0.9,1.03 -2.32,-2.98 -0.49,-1.35 -0.11,-4.54 0.47,-1.5 3.64,-1.58 2.52,0.09 1.15,-1.25 0.92,1.72 0.75,0.61 1.58,-0.39 0.95,-0.04 1.33,0.54 4.12,3.53 5.7,1.9 2.94,1.82 0.91,0.37 1.14,0.07 1.11,-0.15 6.39,-2.03 4.61,-3.69 0.55,-1.47 -1.84,-1.83 -1.01,-1.2 -0.34,-0.78 -0.25,-0.81 -0.26,-1.15 -0.17,-1.83 0.08,-0.9 0.22,-0.96 0.52,-0.77 3.09,-5.73 3.01,-6.85 0.45,-0.98 0.58,-0.67 4.62,-3.79 0.85,-0.5 0.96,-0.42 0.78,-0.56 0.54,-1.2 0.26,-1.02 0.09,-0.64 1.78,-0.31 0.87,0.31 1.47,1.22 3.27,3.18 3.17,4.57 5.39,1.35 2.48,1.15 0.49,1.79 -0.48,0.8 -1.86,0.38 -1.98,0.04 -2.07,-0.18 -0.66,0.59 -0.1,0.95 0.29,1.41 2.88,12.71 0.76,2.69 0.62,2.08 0.75,1.33 0.92,0.65 0.08,0.48 -0.08,1.63 -0.23,1.2 -2.53,2.03 -0.78,-0.31 -0.77,-0.35 -0.83,0.18 -0.93,1.04 -1.13,1.68 -1.12,1.99 -0.31,0.86 -0.92,5.04 -2.26,8.81 -3.17,10.68 z", "fill": "#bfe6c8", "labelX": 212.1, "labelY": 356.7, "fontSize": 10, "showLabel": true, "area": 3017.2}, {"id": "vid", "name": "Vichada", "d": "m 438.66,319.10916 0.7,-0.44 0.91,-0.77 0.75,-0.97 4.5,-7.6 1.72,-0.83 1.18,-0.7 6.52,-6 0.08,-0.85 0,-0.84 0.43,-1.06 1.15,-0.76 0.87,-0.55 7.47,-4.44 3.85,-1.51 1.11,-0.13 2.03,0.06 0.95,-0.17 2.48,-0.6 1.06,-0.34 2.93,-1.87 1.07,-1.2 4.26,-5.6 1.01,-2.72 0.56,-1.74 1.01,-2.14 0.62,-0.94 1.35,-1.63 0.5,-0.35 0.52,-0.33 1.38,-0.59 1.25,-0.22 2.56,0.26 2.36,0.26 2.41,-0.03 1.64,-0.13 2.18,-0.76 1.13,-0.57 1.63,-1.32 1.04,-0.5 1.35,-0.62 2.28,-0.11 0.63,1.06 1.24,1.31 1.19,0.28 1.92,-0.67 1.73,-1.67 1.55,-1.57 1.14,-0.99 1.3,-0.53 1.26,0.05 8.16,1.17 3.06,0.7 1.71,0.51 1.07,0.64 1.97,0.25 3.64,-1.2 3.01,-0.9 0.95,-0.17 1.43,-0.05 1.85,0.5 2.26,0.48 1,-0.32 2.7,-0.95 1.47,-0.5 1.6,-0.49 0.95,-0.03 1.18,0.08 1.54,0.34 1.27,0.32 1.54,-0.07 1.67,-0.43 1.62,-0.84 3.59,-2.86 5.68,0.6 2.39,0.32 2.95,0.94 1.2,0.8 1.58,1.55 0.97,0.45 0.75,0.06 -1.43,1.61 -0.14,1.34 0.29,0.97 0.66,1.16 1.42,1.27 0.87,1.78 -0.51,0.77 -1.46,0.88 -0.71,0.57 -2.18,2.07 -2.69,2.74 -0.94,1.34 -0.95,2.5 -0.36,1.98 0.12,1.28 0.27,1.64 0.35,1.4 0.74,1.24 -1.38,2.87 -1.61,1.22 -2.44,1.5 -0.89,0.22 -1.43,0.97 -1.84,3.15 0.78,7.2 0.38,1.57 0.73,2.21 0.05,2.72 -0.5,5.84 -0.13,1.22 -0.33,2.66 -1.4,7.21 3.05,9.3 -0.68,1.42 -0.18,1.12 -0.03,1.69 0.81,2.68 2.37,3.24 0.85,1.66 -0.92,0.29 -3,1.12 -0.77,0.55 -0.96,1.19 -1.37,1.49 -2,1.48 -0.74,-0.63 -0.09,-1.07 -0.59,-0.79 -3.36,-1.65 -5.42,0 -7.15,0.83 -0.9,0.45 -5.73,5.05 -0.51,0.66 -0.71,1.34 -2.03,0.65 -2.94,-0.2 -2,-0.17 -2.57,0.74 -2.21,2.15 -1.95,1.69 -2.18,-0.93 -4.88,1.04 -6.26,1.23 -0.25,-1.38 -1.09,-0.89 -1.81,-0.76 -3.43,0.49 -1.15,0.98 -2.74,0.37 -2.05,-1.06 -3.77,0.21 -0.83,0.89 0.27,1.42 -0.1,1.01 -1.53,1.5 -2.56,1.25 -1.92,0.32 -4.53,1.77 -4.87,4.28 -2.04,0 -1.15,-0.68 -3.39,1.21 -1.35,1.78 0.6,1.35 0.66,0.96 0.27,3.03 -1.8,0.32 -1.64,0.01 -1.69,0.44 -2.06,3.47 -0.29,3.26 0.31,1.74 0.1,1.27 -3.08,4.22 -1.04,0.46 -1.93,0.51 -1.97,0.35 -0.69,0.32 -1.07,-0.33 -2.1,-0.94 -2.67,-0.99 -0.63,0.99 -0.42,1.77 -1.13,1.01 -4.2,-0.21 -2.35,-1.27 -4.55,-1.35 -3.72,0.67 -0.3,-2.14 -0.05,-0.53 -0.02,-5.6 -0.03,-10.52 -0.03,-25.31 -0.04,-10.54 -0.02,-9.15 -0.02,-21.15 z", "fill": "#cfc3e8", "labelX": 514.2, "labelY": 333.9, "fontSize": 12.5, "showLabel": true, "area": 13676.9}, {"id": "vau", "name": "Vaupés", "d": "m 506.27,561.61916 -1.01,2.19 0.14,3.16 -6.72,0.9 -0.78,-3.54 0.06,-0.91 -3.25,-2.81 -4.23,1.02 -2.85,1.32 -0.82,0.3 -1.36,-0.23 -0.29,-0.84 1.12,-3.18 -0.2,-1.52 -5.83,0.39 -1.36,0.88 -0.65,0.88 -0.06,0.84 0.59,0.66 1.19,0.3 0.6,0.61 -0.32,0.95 -0.69,0.77 -0.84,0.36 -1.15,-0.09 -5.07,-4.02 -0.51,-0.86 -0.32,-0.98 0.27,-0.89 1.42,-0.83 1.08,-0.84 -0.34,-1.76 -0.95,-0.98 -1.04,-0.9 -0.06,-1.57 1.33,-2.12 -0.06,-4.82 1.5,-5.54 -0.71,-0.92 -2.02,-1.06 -2.46,1.85 0.72,1.21 -1.46,0.33 -2.75,-0.9 -1.32,-1.24 -0.6,-0.94 -1.61,-1.66 -10.41,-3.36 -0.7,1.33 -3.01,1.22 -1.62,-2.64 -1.69,-7.58 -1.04,-1.96 -2.08,-2.2 -1.58,0.65 -4.11,-1.3 -8.52,-5.18 -0.98,-0.75 -1.89,-0.93 -3.04,-0.14 -0.76,0.62 -0.39,0.42 -0.91,0.25 -3.81,-2.1 -3.27,-2.07 -3,-2.73 -2.59,-0.66 -1.44,-4.41 -2.74,-4.78 -2.77,-3.2 -0.8,-0.69 0.07,-0.12 0.73,-0.81 5.29,-5.05 3.59,-3.38 0.25,-1.12 0.36,-1.25 0.55,-0.83 1.31,-1.01 1.36,-0.32 1,-0.12 2.62,-2.55 3.08,-4.22 0.02,-2.2 -0.17,-1.14 -0.07,-1.07 2.49,-6.2 0.69,-1.18 2.85,-1.97 5.08,-5.72 2.78,-3.73 4.03,-2.49 1.25,-0.26 1.87,0.07 0.89,-0.43 5.39,-4.19 4.67,0.38 2.31,0.04 2.17,-0.21 12.49,-3.43 7.48,-2.87 1.04,0.04 0.11,0.23 0.51,2.37 -0.63,0.93 -0.99,0.49 0.28,3.72 0.97,1.37 2.07,1.78 1.62,1.27 1.19,0.41 1.28,0.08 1.14,0.17 3.78,0.92 1.37,1.12 0.15,0.51 0,25.63 5.11,-0.01 4.32,-0.23 7.35,1.62 2.41,-0.74 1.58,-0.67 3.03,1.6 1.52,1.42 3.61,5.55 -0.78,4.53 1.3,4.46 -3.38,1.13 -3.2,-0.27 -1.71,-1.37 -5.37,-3.28 -9.24,2.43 -2.74,1.77 -1.89,1.33 -5.22,0.15 -2.52,0 -2.52,0.52 -0.07,3.02 -0.08,5.85 -0.05,2.52 -0.12,6.68 -0.13,5.88 -0.08,3.61 -0.02,2.84 1.5,1.89 3.63,4.12 8,6.2 0.92,0.21 1.18,0.24 2.39,1.12 0.99,1.06 1.36,4.71 -0.38,1.35 -0.56,1.33 -0.78,0.98 0.11,1.29 3.91,7.27 1.52,0.88 1.92,1.89 z", "fill": "#fdf1a8", "labelX": 459.3, "labelY": 501.4, "fontSize": 10, "showLabel": true, "area": 7114.0}];
  var DATA = [{"id": 1, "uni": "Universidad de Antioquia", "corto": "U. Antioquia", "uniBase": "Universidad de Antioquia", "ciudad": "Medellín", "depto": "Antioquia", "deptoId": "ant", "sector": "publica", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 165, "semestres": 10, "costo": 739258, "vigencia": 7, "nota": ""}, {"id": 2, "uni": "Universidad de Cartagena", "corto": "U. Cartagena", "uniBase": "Universidad de Cartagena", "ciudad": "Cartagena", "depto": "Bolívar", "deptoId": "bol", "sector": "publica", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 185, "semestres": 10, "costo": 918517, "vigencia": 8, "nota": ""}, {"id": 3, "uni": "Pontificia Universidad Javeriana", "corto": "Javeriana", "uniBase": "Pontificia Universidad Javeriana", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 148, "semestres": 8, "costo": 14160505, "vigencia": 7, "nota": ""}, {"id": 4, "uni": "Universidad El Bosque", "corto": "El Bosque", "uniBase": "Universidad El Bosque", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 158, "semestres": 9, "costo": 9657000, "vigencia": 7, "nota": "Vigencia transitoria hasta 30/09/2025 (Artículo transitorio 2.5.3.2.12.1, literal B, Decreto 1174 de 2023)."}, {"id": 5, "uni": "Universidad de La Salle", "corto": "La Salle", "uniBase": "Universidad de La Salle", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(o)", "creditos": 170, "semestres": 10, "costo": 8725000, "vigencia": 7, "nota": ""}, {"id": 6, "uni": "Universidad Santiago de Cali", "corto": "Sgo. de Cali", "uniBase": "Universidad Santiago de Cali", "ciudad": "Cali", "depto": "Valle del Cauca", "deptoId": "vac", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 159, "semestres": 10, "costo": 6032080, "vigencia": 7, "nota": ""}, {"id": 7, "uni": "Universidad Autónoma de Bucaramanga (UNAB)", "corto": "UNAB", "uniBase": "Universidad Autónoma de Bucaramanga", "ciudad": "Bucaramanga", "depto": "Santander", "deptoId": "san", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 151, "semestres": 9, "costo": null, "vigencia": 7, "nota": ""}, {"id": 8, "uni": "Universidad Icesi", "corto": "Icesi", "uniBase": "Universidad Icesi", "ciudad": "Cali", "depto": "Valle del Cauca", "deptoId": "vac", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 180, "semestres": 10, "costo": 14320482, "vigencia": 8, "nota": ""}, {"id": 9, "uni": "Universidad de Ciencias Aplicadas y Ambientales (UDCA)", "corto": "UDCA", "uniBase": "Universidad de Ciencias Aplicadas y Ambientales", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 190, "semestres": 10, "costo": 8139041, "vigencia": 7, "nota": ""}, {"id": 10, "uni": "Universidad CES", "corto": "U. CES", "uniBase": "Universidad CES", "ciudad": "Medellín", "depto": "Antioquia", "deptoId": "ant", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 181, "semestres": 10, "costo": 9333932, "vigencia": 7, "nota": ""}, {"id": 11, "uni": "Fundación Universitaria Sanitas", "corto": "Sanitas", "uniBase": "Fundación Universitaria Sanitas", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 181, "semestres": 10, "costo": null, "vigencia": 7, "nota": ""}, {"id": 12, "uni": "Fundación Universitaria Salesiana", "corto": "Salesiana", "uniBase": "Fundación Universitaria Salesiana", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "privada", "programa": "Química Farmacéutica", "titulo": "Químico Farmacéutico", "creditos": 170, "semestres": 10, "costo": 7714000, "vigencia": 7, "nota": ""}, {"id": 13, "uni": "Universidad Simón Bolívar", "corto": "Simón Bolívar", "uniBase": "Universidad Simón Bolívar", "ciudad": "Barranquilla", "depto": "Atlántico", "deptoId": "atl", "sector": "privada", "programa": "Química y Farmacia", "titulo": "Químico Farmacéutico", "creditos": 160, "semestres": 10, "costo": 6542675, "vigencia": 7, "nota": ""}, {"id": 14, "uni": "Universidad Nacional de Colombia (Bogotá)", "corto": "U. Nacional (Bogotá)", "uniBase": "Universidad Nacional de Colombia", "ciudad": "Bogotá", "depto": "Bogotá D.C.", "deptoId": "dc", "sector": "publica", "programa": "Farmacia", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 185, "semestres": 10, "costo": null, "vigencia": 10, "nota": "Acreditación de Alta Calidad (registrada desde 1998)."}, {"id": 15, "uni": "Universidad Nacional de Colombia (Medellín)", "corto": "U. Nacional (Medellín)", "uniBase": "Universidad Nacional de Colombia", "ciudad": "Medellín", "depto": "Antioquia", "deptoId": "ant", "sector": "publica", "programa": "Farmacia", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 185, "semestres": 10, "costo": null, "vigencia": null, "nota": "Registro calificado con ejecutoria 03-12-2025 (extensión de sede)."}, {"id": 16, "uni": "Universidad Nacional de Colombia (Palmira)", "corto": "U. Nacional (Palmira)", "uniBase": "Universidad Nacional de Colombia", "ciudad": "Palmira", "depto": "Valle del Cauca", "deptoId": "vac", "sector": "publica", "programa": "Farmacia", "titulo": "Químico(a) Farmacéutico(a)", "creditos": 185, "semestres": 10, "costo": null, "vigencia": null, "nota": "Registro calificado con ejecutoria 27-04-2026 (extensión de sede)."}, {"id": 17, "uni": "Universidad del Atlántico", "corto": "U. del Atlántico", "uniBase": "Universidad del Atlántico", "ciudad": "Barranquilla", "depto": "Atlántico", "deptoId": "atl", "sector": "publica", "programa": "Farmacia", "titulo": "Químico Farmacéutico", "creditos": 180, "semestres": 10, "costo": 703799, "vigencia": 6, "nota": "Acreditación de Alta Calidad. Admisiones anuales (no semestrales, a diferencia del resto)."}];
  var CITY_COORDS = {"Medellín": {"x": 269, "y": 238}, "Cartagena": {"x": 268, "y": 103}, "Bogotá": {"x": 304.6, "y": 310.4}, "Cali": {"x": 205, "y": 374}, "Palmira": {"x": 222, "y": 367}, "Bucaramanga": {"x": 344, "y": 234}, "Barranquilla": {"x": 278, "y": 81}};
  var CITY_LABEL_POS = {"Medellín": {"x": 269, "y": 208, "anchor": "middle"}, "Cartagena": {"x": 268, "y": 90, "anchor": "middle"}, "Bogotá": {"x": 304.6, "y": 286, "anchor": "middle"}, "Cali": {"x": 194, "y": 374, "anchor": "end"}, "Palmira": {"x": 233, "y": 367, "anchor": "start"}, "Bucaramanga": {"x": 355, "y": 234, "anchor": "start"}, "Barranquilla": {"x": 278, "y": 64, "anchor": "middle"}};
  // "cun" (Cundinamarca) se incluye aquí solo para que se vea resaltada
  // en el mapa, ya que ahí se dibujan los 7 puntos de Bogotá, D.C. por
  // falta de espacio en ese departamento. Administrativamente los
  // programas siguen contados en Bogotá, D.C. (ver notas del análisis).
  var DEPTS_WITH_PROGRAMS = ["ant", "atl", "bol", "dc", "san", "vac", "cun"];

  var svgNS = "http://www.w3.org/2000/svg";

  /* ============================================================
     2. UTILIDADES
     ============================================================ */
  function escapeHtml(str){
    var div = document.createElement("div");
    div.textContent = str === undefined || str === null ? "" : String(str);
    return div.innerHTML;
  }
  function fmtCOP(n){
    if(n === null || n === undefined) return "";
    return "$" + Number(n).toLocaleString("es-CO");
  }
  function costoText(d){
    if(d.sector === "publica"){
      var extra = (d.costo != null)
        ? "<span class=\"popup-subnote\">(dato SNIES de referencia: " + fmtCOP(d.costo) + ")</span>"
        : "";
      return "Uni. Pública — Costo: $0" + extra;
    }
    return d.costo != null ? (fmtCOP(d.costo) + " / semestre") : "Dato no disponible en SNIES";
  }

  /* ============================================================
     3. POSICIONES DE MARCADORES
     ============================================================
     Cada posición fue calculada y verificada de antemano (punto por
     punto) para caer DENTRO del polígono real del departamento al que
     pertenece — no solo dentro de su rectángulo delimitador. Cuando un
     departamento es muy pequeño para separar varios puntos en círculo
     (p. ej. Bogotá, D.C., el departamento más pequeño en área pero con
     7 programas), los puntos se alinean en una fila muy compacta y se
     reduce su tamaño (radio) para que sigan cabiendo dentro del límite,
     en vez de invadir el departamento vecino. */
  var MARKER_POS = {
    // Cada punto fue verificado por computadora: el círculo completo
    // (centro + 48 puntos de su circunferencia) cae dentro del polígono
    // real de su departamento, no solo el centro. Cuando no cupieron
    // varios puntos del tamaño normal (r=7) sin salirse, se redujo su
    // radio hasta que sí cupieran — nunca se dejó un punto fuera.

    // Medellín (Antioquia) — 3 puntos, radio normal
    "1":  {x:269.00, y:220.50, r:7},   // U. de Antioquia
    "10": {x:284.16, y:246.75, r:7},   // U. CES
    "15": {x:253.84, y:246.75, r:7},   // U. Nacional (Medellín)

    // Cartagena (Bolívar) — punto único, radio normal
    "2":  {x:268.00, y:103.00, r:7},   // U. de Cartagena

    // Bogotá — Bogotá, D.C. es el departamento más pequeño del país en
    // área y no tiene espacio para separar 7 puntos con claridad, así
    // que se distribuyen dentro de Cundinamarca (el departamento que
    // rodea a Bogotá, D.C.), muy cerca de su ubicación real. El
    // programa sigue registrado administrativamente en Bogotá, D.C.
    // — eso no cambia, solo cambia dónde se dibuja el punto en el mapa.
    "3":  {x:304.60, y:298.90, r:4.5}, // Javeriana
    "4":  {x:313.59, y:303.23, r:4.5}, // El Bosque
    "5":  {x:315.81, y:312.96, r:4.5}, // La Salle
    "9":  {x:309.59, y:320.76, r:4.5}, // UDCA
    "11": {x:299.61, y:320.76, r:4.5}, // Sanitas
    "12": {x:293.39, y:312.96, r:4.5}, // Salesiana
    "14": {x:295.61, y:303.23, r:4.5}, // U. Nacional (Bogotá)

    // Cali (Valle del Cauca) — 2 puntos, radio normal
    "6":  {x:205.00, y:363.50, r:7},   // Santiago de Cali
    "8":  {x:205.00, y:384.50, r:7},   // Icesi

    // Palmira (Valle del Cauca) — punto único, radio normal
    "16": {x:222.00, y:367.00, r:7},   // U. Nacional (Palmira)

    // Bucaramanga (Santander) — punto único, radio normal
    "7":  {x:344.00, y:234.00, r:7},   // UNAB

    // Barranquilla (Atlántico) — 2 puntos, radio reducido a 5 (el
    // departamento es angosto en ese punto) para que quepan sin solaparse
    "13": {x:278.00, y:75.50, r:5},    // Simón Bolívar
    "17": {x:278.00, y:86.50, r:5}     // U. del Atlántico
  };

  /* ============================================================
     4. MAPA — departamentos (base cartográfica real)
     ============================================================ */
  function renderDepartments(){
    var g = document.getElementById("departmentsLayer");
    var gl = document.getElementById("deptLabelsLayer");
    g.innerHTML = "";
    gl.innerHTML = "";
    var withProgramsSet = {};
    DEPTS_WITH_PROGRAMS.forEach(function(id){ withProgramsSet[id] = true; });

    DEPARTMENTS.forEach(function(dep){
      var path = document.createElementNS(svgNS, "path");
      path.setAttribute("d", dep.d);
      path.setAttribute("fill", dep.fill);
      var hasPrograms = !!withProgramsSet[dep.id];
      path.setAttribute("class", "dept-shape" + (hasPrograms ? " has-programs" : ""));
      path.setAttribute("fill-opacity", hasPrograms ? "1" : "0.42");
      var title = document.createElementNS(svgNS, "title");
      title.textContent = dep.name + (hasPrograms ? " — tiene programas registrados" : "");
      path.appendChild(title);
      g.appendChild(path);

      if(dep.showLabel){
        var t = document.createElementNS(svgNS, "text");
        t.setAttribute("x", dep.labelX);
        t.setAttribute("y", dep.labelY);
        t.setAttribute("text-anchor", "middle");
        t.setAttribute("class", "dept-label");
        t.setAttribute("font-size", dep.fontSize);
        t.textContent = dep.name.toUpperCase();
        gl.appendChild(t);
      }
    });
  }

  function renderSideLegend(){
    var g = document.getElementById("sideLegendLayer");
    g.innerHTML = "";
    function line(x, y, text, cls){
      var t = document.createElementNS(svgNS, "text");
      t.setAttribute("x", x);
      t.setAttribute("y", y);
      t.setAttribute("class", cls || "side-legend");
      t.textContent = text;
      g.appendChild(t);
    }
    // Departamentos muy pequeños para rotular directamente sobre el mapa
    line(8, 400, "RISARALDA", "side-legend-title");
    line(8, 412, "QUINDÍO", "side-legend-title");
    line(8, 424, "BOGOTÁ, D.C.", "side-legend-title");
    // Nota del archipiélago (fuera de escala, como en el mapa de referencia)
    line(8, 70, "SAN ANDRÉS, PROVIDENCIA Y", "side-legend");
    line(8, 80, "SANTA CATALINA (fuera de escala)", "side-legend");
  }

  /* ============================================================
     5. MAPA — etiquetas de ciudad y marcadores
     ============================================================ */
  function renderCityLabels(){
    var g = document.getElementById("cityLabelsLayer");
    g.innerHTML = "";
    Object.keys(CITY_LABEL_POS).forEach(function(city){
      var p = CITY_LABEL_POS[city];
      var approxWidth = city.length * 5.6 + 6;
      var bg = document.createElementNS(svgNS, "rect");
      var bx = p.anchor === "middle" ? p.x - approxWidth/2 : (p.anchor === "end" ? p.x - approxWidth : p.x);
      bg.setAttribute("x", bx - 2);
      bg.setAttribute("y", p.y - 9);
      bg.setAttribute("width", approxWidth + 4);
      bg.setAttribute("height", 12);
      bg.setAttribute("rx", 3);
      bg.setAttribute("class", "city-label-bg");
      g.appendChild(bg);

      var t = document.createElementNS(svgNS, "text");
      t.setAttribute("x", p.x);
      t.setAttribute("y", p.y);
      t.setAttribute("text-anchor", p.anchor);
      t.setAttribute("class", "city-label");
      t.textContent = city;
      g.appendChild(t);
    });
  }

  function renderMarkers(){
    var g = document.getElementById("markersLayer");
    g.innerHTML = "";
    DATA.forEach(function(d){
      var p = MARKER_POS[d.id];
      var marker = document.createElementNS(svgNS, "g");
      marker.setAttribute("class", "marker");
      marker.setAttribute("data-id", d.id);
      marker.setAttribute("tabindex", "0");
      marker.setAttribute("role", "button");
      marker.setAttribute("aria-label", d.uni + ", " + d.ciudad);

      var baseR = p.r || 7;
      var circle = document.createElementNS(svgNS, "circle");
      circle.setAttribute("cx", p.x);
      circle.setAttribute("cy", p.y);
      circle.setAttribute("r", baseR);
      circle.setAttribute("data-base-r", baseR);
      circle.setAttribute("class", "marker-dot " + d.sector);
      marker.appendChild(circle);

      marker.addEventListener("mouseenter", function(){
        circle.setAttribute("r", baseR + 2.2);
      });
      marker.addEventListener("mouseleave", function(){
        if(!marker.classList.contains("selected")) circle.setAttribute("r", baseR);
      });
      marker.addEventListener("click", function(e){
        e.stopPropagation();
        onMarkerActivate(d, marker);
      });
      marker.addEventListener("keypress", function(e){
        if(e.key === "Enter" || e.key === " "){
          e.preventDefault();
          onMarkerActivate(d, marker);
        }
      });
      g.appendChild(marker);
    });
  }

  function onMarkerActivate(d, markerEl){
    document.querySelectorAll(".marker.selected").forEach(function(m){
      m.classList.remove("selected");
      var c = m.querySelector(".marker-dot");
      if(c) c.setAttribute("r", c.getAttribute("data-base-r"));
    });
    markerEl.classList.add("selected");
    var selCircle = markerEl.querySelector(".marker-dot");
    if(selCircle) selCircle.setAttribute("r", parseFloat(selCircle.getAttribute("data-base-r")) + 2.2);
    showPopup(d, markerEl);
    highlightListItem(d.id);
  }

  /* ============================================================
     6. POPUP
     ============================================================ */
  function popupContentHTML(d){
    var sectorLabel = d.sector === "publica" ? "Pública" : "Privada";
    var notaHTML = d.nota ? "<div class=\"popup-note\">⚠ " + escapeHtml(d.nota) + "</div>" : "";
    return (
      "<button type=\"button\" class=\"popup-close\" aria-label=\"Cerrar\">×</button>" +
      "<span class=\"sector-tag " + d.sector + "\">" + sectorLabel + "</span>" +
      "<h3>" + escapeHtml(d.uni) + "</h3>" +
      "<div class=\"popup-city\">" + escapeHtml(d.ciudad) + ", " + escapeHtml(d.depto) + "</div>" +
      "<dl>" +
        "<dt>Programa</dt><dd>" + escapeHtml(d.programa) + "</dd>" +
        "<dt>Título</dt><dd>" + escapeHtml(d.titulo) + "</dd>" +
        "<dt>Semestres</dt><dd>" + d.semestres + "</dd>" +
        "<dt>Créditos</dt><dd>" + d.creditos + "</dd>" +
        "<dt>Costo/semestre</dt><dd>" + costoText(d) + "</dd>" +
        "<dt>Vigencia registro</dt><dd>" + (d.vigencia ? d.vigencia + " años" : "No reportada") + "</dd>" +
      "</dl>" +
      notaHTML
    );
  }

  function showPopup(d, anchorEl){
    var popup = document.getElementById("popup");
    popup.innerHTML = popupContentHTML(d);
    popup.classList.remove("hidden");
    positionPopup(anchorEl);
    var closeBtn = popup.querySelector(".popup-close");
    if(closeBtn) closeBtn.addEventListener("click", hidePopup);
  }

  function positionPopup(anchorEl){
    var popup = document.getElementById("popup");
    var mapPanel = document.getElementById("mapPanel");
    var anchorRect = anchorEl.getBoundingClientRect();
    var panelRect = mapPanel.getBoundingClientRect();
    var popupWidth = 260;

    var left = (anchorRect.left - panelRect.left) + anchorRect.width / 2 + 14;
    var top = (anchorRect.top - panelRect.top) - 10;

    if(left + popupWidth > panelRect.width - 8){
      left = (anchorRect.left - panelRect.left) - popupWidth - 14;
    }
    if(left < 8) left = 8;
    if(top < 8) top = 8;
    var maxTop = panelRect.height - 40;
    if(top > maxTop) top = maxTop;

    popup.style.left = left + "px";
    popup.style.top = top + "px";
  }

  function hidePopup(){
    var popup = document.getElementById("popup");
    popup.classList.add("hidden");
    document.querySelectorAll(".marker.selected").forEach(function(m){
      m.classList.remove("selected");
      var c = m.querySelector(".marker-dot");
      if(c) c.setAttribute("r", c.getAttribute("data-base-r"));
    });
    document.querySelectorAll(".list-item.active").forEach(function(it){ it.classList.remove("active"); });
  }

  document.addEventListener("click", function(e){
    var popup = document.getElementById("popup");
    if(popup.classList.contains("hidden")) return;
    if(popup.contains(e.target)) return;
    if(e.target.closest && e.target.closest(".marker")) return;
    if(e.target.closest && e.target.closest(".list-item")) return;
    hidePopup();
  });
  window.addEventListener("resize", hidePopup);

  /* ============================================================
     7. LISTA
     ============================================================ */
  function renderList(data){
    var listEl = document.getElementById("programList");
    listEl.innerHTML = "";
    document.getElementById("listCount").textContent = data.length;

    if(data.length === 0){
      listEl.innerHTML = "<div class=\"empty-list\">Ningún programa coincide con los filtros seleccionados.</div>";
      return;
    }

    data.forEach(function(d){
      var item = document.createElement("div");
      item.className = "list-item";
      item.setAttribute("data-id", d.id);
      item.setAttribute("tabindex", "0");

      var dot = document.createElement("span");
      dot.className = "dot " + d.sector;

      var body = document.createElement("div");
      body.className = "list-item-body";
      var title = document.createElement("div");
      title.className = "list-item-title";
      title.textContent = d.uni;
      var sub = document.createElement("div");
      sub.className = "list-item-sub";
      sub.textContent = d.ciudad + " (" + d.depto + ") · " + d.programa + " · " + d.semestres + " sem · " + d.creditos + " créd.";
      body.appendChild(title);
      body.appendChild(sub);

      item.appendChild(dot);
      item.appendChild(body);

      item.addEventListener("click", function(e){
        e.stopPropagation();
        var markerEl = document.querySelector(".marker[data-id='" + d.id + "']");
        if(markerEl) onMarkerActivate(d, markerEl);
      });

      listEl.appendChild(item);
    });
  }

  function highlightListItem(id){
    document.querySelectorAll(".list-item").forEach(function(it){
      it.classList.toggle("active", String(it.getAttribute("data-id")) === String(id));
    });
    var activeItem = document.querySelector(".list-item[data-id='" + id + "']");
    if(activeItem) activeItem.scrollIntoView({block:"nearest"});
  }

  /* ============================================================
     8. GRÁFICOS DE BARRAS (SVG genérico, sin librerías externas)
     ============================================================ */
  function renderBarChart(container, items){
    container.innerHTML = "";
    if(!items || items.length === 0){
      container.innerHTML = "<p class=\"empty-msg\">Sin datos para mostrar con los filtros actuales.</p>";
      return;
    }
    var VBWIDTH = 520;
    var LEFTLABEL = 172;
    var RIGHTPAD = 74;
    var BARHEIGHT = 18;
    var GAP = 9;
    var chartWidth = VBWIDTH - LEFTLABEL - RIGHTPAD;

    var maxTotal = 0;
    items.forEach(function(it){
      var t = it.segments.reduce(function(s, seg){ return s + seg.value; }, 0);
      if(t > maxTotal) maxTotal = t;
    });
    if(maxTotal <= 0) maxTotal = 1;

    var height = items.length * (BARHEIGHT + GAP) + GAP;
    var svg = document.createElementNS(svgNS, "svg");
    svg.setAttribute("viewBox", "0 0 " + VBWIDTH + " " + height);
    svg.setAttribute("width", "100%");
    svg.setAttribute("height", height);

    var axis = document.createElementNS(svgNS, "line");
    axis.setAttribute("x1", LEFTLABEL);
    axis.setAttribute("x2", LEFTLABEL);
    axis.setAttribute("y1", 0);
    axis.setAttribute("y2", height);
    axis.setAttribute("class", "chart-axis");
    svg.appendChild(axis);

    items.forEach(function(it, i){
      var y = GAP + i * (BARHEIGHT + GAP);

      var label = document.createElementNS(svgNS, "text");
      label.setAttribute("x", LEFTLABEL - 8);
      label.setAttribute("y", y + BARHEIGHT * 0.7);
      label.setAttribute("text-anchor", "end");
      label.setAttribute("class", "chart-label");
      label.textContent = it.label;
      svg.appendChild(label);

      var xCursor = LEFTLABEL;
      it.segments.forEach(function(seg){
        if(!seg.value || seg.value <= 0) return;
        var w = (seg.value / maxTotal) * chartWidth;
        var rect = document.createElementNS(svgNS, "rect");
        rect.setAttribute("x", xCursor);
        rect.setAttribute("y", y);
        rect.setAttribute("width", Math.max(w, 1));
        rect.setAttribute("height", BARHEIGHT);
        rect.setAttribute("rx", 3);
        rect.setAttribute("fill", seg.color);
        var title = document.createElementNS(svgNS, "title");
        title.textContent = seg.title || String(seg.value);
        rect.appendChild(title);
        svg.appendChild(rect);
        xCursor += w;
      });

      var valLabel = document.createElementNS(svgNS, "text");
      valLabel.setAttribute("x", xCursor + 7);
      valLabel.setAttribute("y", y + BARHEIGHT * 0.7);
      valLabel.setAttribute("class", "chart-value");
      valLabel.textContent = it.displayValue !== undefined ? it.displayValue : "";
      svg.appendChild(valLabel);
    });

    container.appendChild(svg);
  }

  function groupCount(data, keyFn){
    var map = {};
    data.forEach(function(d){
      var k = keyFn(d);
      if(!map[k]) map[k] = {publica:0, privada:0};
      map[k][d.sector]++;
    });
    return map;
  }

  function stackedItemsFromGroup(map, order){
    var keys = order || Object.keys(map).sort(function(a, b){
      return (map[b].publica + map[b].privada) - (map[a].publica + map[a].privada);
    });
    return keys.map(function(k){
      var g = map[k];
      return {
        label: k,
        segments: [
          {value:g.publica, color:COLOR_PUBLIC, title:"Pública: " + g.publica},
          {value:g.privada, color:COLOR_PRIVATE, title:"Privada: " + g.privada}
        ],
        displayValue: g.publica + g.privada
      };
    });
  }

  /* ============================================================
     9. ANÁLISIS (recalcula con los datos filtrados)
     ============================================================ */
  function renderAnalysis(data){
    document.getElementById("analysisCount").textContent = data.length;

    renderBarChart(document.getElementById("chartDepartamento"),
      stackedItemsFromGroup(groupCount(data, function(d){ return d.depto; })));

    renderBarChart(document.getElementById("chartCiudad"),
      stackedItemsFromGroup(groupCount(data, function(d){ return d.ciudad; })));

    var semMap = groupCount(data, function(d){ return d.semestres + " sem"; });
    var semOrder = ["8 sem", "9 sem", "10 sem"].filter(function(k){ return semMap[k]; });
    renderBarChart(document.getElementById("chartSemestres"), stackedItemsFromGroup(semMap, semOrder));

    renderBarChart(document.getElementById("chartPrograma"),
      stackedItemsFromGroup(groupCount(data, function(d){ return d.programa; })));

    var credItems = data.slice().sort(function(a, b){ return b.creditos - a.creditos; }).map(function(d){
      return {
        label: d.corto,
        segments: [{value:d.creditos, color: d.sector === "publica" ? COLOR_PUBLIC : COLOR_PRIVATE, title:d.creditos + " créditos"}],
        displayValue: d.creditos
      };
    });
    renderBarChart(document.getElementById("chartCreditos"), credItems);

    var privConCosto = data.filter(function(d){ return d.sector === "privada" && d.costo != null; })
      .sort(function(a, b){ return b.costo - a.costo; });
    var costoItems = privConCosto.map(function(d){
      return {
        label: d.corto,
        segments: [{value:d.costo, color:COLOR_PRIVATE, title:fmtCOP(d.costo)}],
        displayValue: fmtCOP(d.costo)
      };
    });
    renderBarChart(document.getElementById("chartCosto"), costoItems);
  }

  /* ============================================================
     10. KPIs
     ============================================================ */
  function updateKPIs(data){
    var total = data.length;
    var instituciones = {};
    data.forEach(function(d){ instituciones[d.uniBase] = true; });
    var pub = data.filter(function(d){ return d.sector === "publica"; }).length;
    var priv = total - pub;
    var avgCred = total ? (data.reduce(function(s, d){ return s + d.creditos; }, 0) / total) : 0;
    var avgSem = total ? (data.reduce(function(s, d){ return s + d.semestres; }, 0) / total) : 0;

    document.getElementById("kpiTotal").textContent = total;
    document.getElementById("kpiInst").textContent = Object.keys(instituciones).length;
    document.getElementById("kpiPub").textContent = total ? Math.round(pub / total * 100) + "%" : "—";
    document.getElementById("kpiPriv").textContent = total ? Math.round(priv / total * 100) + "%" : "—";
    document.getElementById("kpiCred").textContent = total ? avgCred.toFixed(1) : "—";
    document.getElementById("kpiSem").textContent = total ? avgSem.toFixed(1) : "—";
  }

  /* ============================================================
     11. FILTROS
     ============================================================ */
  function buildFilterControls(){
    var pubCount = DATA.filter(function(d){ return d.sector === "publica"; }).length;
    var privCount = DATA.filter(function(d){ return d.sector === "privada"; }).length;
    document.getElementById("countPublica").textContent = pubCount;
    document.getElementById("countPrivada").textContent = privCount;

    var cityCounts = groupCount(DATA, function(d){ return d.ciudad; });
    var cities = Object.keys(cityCounts).sort(function(a, b){
      var ta = cityCounts[a].publica + cityCounts[a].privada;
      var tb = cityCounts[b].publica + cityCounts[b].privada;
      return tb - ta;
    });
    var cityWrap = document.getElementById("cityCheckboxes");
    cities.forEach(function(city){
      var total = cityCounts[city].publica + cityCounts[city].privada;
      var row = document.createElement("div");
      row.className = "check-row";
      row.innerHTML =
        "<label><input type=\"checkbox\" class=\"city-checkbox\" value=\"" + escapeHtml(city) + "\" checked>" +
        escapeHtml(city) + "</label><span class=\"count\">" + total + "</span>";
      cityWrap.appendChild(row);
    });

    var deptCounts = groupCount(DATA, function(d){ return d.depto; });
    var depts = Object.keys(deptCounts).sort(function(a, b){
      var ta = deptCounts[a].publica + deptCounts[a].privada;
      var tb = deptCounts[b].publica + deptCounts[b].privada;
      return tb - ta;
    });
    var deptWrap = document.getElementById("deptCheckboxes");
    depts.forEach(function(dep){
      var total = deptCounts[dep].publica + deptCounts[dep].privada;
      var row = document.createElement("div");
      row.className = "check-row";
      row.innerHTML =
        "<label><input type=\"checkbox\" class=\"dept-checkbox\" value=\"" + escapeHtml(dep) + "\" checked>" +
        escapeHtml(dep) + "</label><span class=\"count\">" + total + "</span>";
      deptWrap.appendChild(row);
    });

    document.getElementById("citySummary").textContent = cities.length + "/" + cities.length;
    document.getElementById("deptSummary").textContent = depts.length + "/" + depts.length;
  }

  function updateFilterSummaries(){
    var sectorChecked = document.querySelectorAll(".sector-checkbox:checked").length;
    var sectorTotal = document.querySelectorAll(".sector-checkbox").length;
    document.getElementById("sectorSummary").textContent = sectorChecked + "/" + sectorTotal;

    var cityChecked = document.querySelectorAll(".city-checkbox:checked").length;
    var cityTotal = document.querySelectorAll(".city-checkbox").length;
    document.getElementById("citySummary").textContent = cityChecked + "/" + cityTotal;

    var deptChecked = document.querySelectorAll(".dept-checkbox:checked").length;
    var deptTotal = document.querySelectorAll(".dept-checkbox").length;
    document.getElementById("deptSummary").textContent = deptChecked + "/" + deptTotal;
  }

  function getFilteredData(){
    var sectors = [];
    if(document.getElementById("sectorPublica").checked) sectors.push("publica");
    if(document.getElementById("sectorPrivada").checked) sectors.push("privada");

    var cityCheckboxes = document.querySelectorAll(".city-checkbox:checked");
    var cities = Array.prototype.map.call(cityCheckboxes, function(cb){ return cb.value; });

    var deptCheckboxes = document.querySelectorAll(".dept-checkbox:checked");
    var depts = Array.prototype.map.call(deptCheckboxes, function(cb){ return cb.value; });

    var search = document.getElementById("searchInput").value.trim().toLowerCase();

    return DATA.filter(function(d){
      if(sectors.indexOf(d.sector) === -1) return false;
      if(cities.indexOf(d.ciudad) === -1) return false;
      if(depts.indexOf(d.depto) === -1) return false;
      if(search !== "" &&
         d.uni.toLowerCase().indexOf(search) === -1 &&
         d.programa.toLowerCase().indexOf(search) === -1 &&
         d.ciudad.toLowerCase().indexOf(search) === -1 &&
         d.depto.toLowerCase().indexOf(search) === -1){
        return false;
      }
      return true;
    });
  }

  function applyFilters(){
    updateFilterSummaries();
    var filtered = getFilteredData();
    var filteredIds = {};
    filtered.forEach(function(d){ filteredIds[d.id] = true; });

    document.querySelectorAll(".marker").forEach(function(m){
      var id = m.getAttribute("data-id");
      m.style.display = filteredIds[id] ? "" : "none";
    });

    renderList(filtered);
    renderAnalysis(filtered);
    updateKPIs(filtered);
    hidePopup();
  }

  function wireFilterEvents(){
    document.getElementById("sectorPublica").addEventListener("change", applyFilters);
    document.getElementById("sectorPrivada").addEventListener("change", applyFilters);
    document.getElementById("searchInput").addEventListener("input", applyFilters);

    document.querySelectorAll(".city-checkbox").forEach(function(cb){
      cb.addEventListener("change", applyFilters);
    });
    document.getElementById("cityAllBtn").addEventListener("click", function(){
      document.querySelectorAll(".city-checkbox").forEach(function(cb){ cb.checked = true; });
      applyFilters();
    });
    document.getElementById("cityNoneBtn").addEventListener("click", function(){
      document.querySelectorAll(".city-checkbox").forEach(function(cb){ cb.checked = false; });
      applyFilters();
    });

    document.querySelectorAll(".dept-checkbox").forEach(function(cb){
      cb.addEventListener("change", applyFilters);
    });
    document.getElementById("deptAllBtn").addEventListener("click", function(){
      document.querySelectorAll(".dept-checkbox").forEach(function(cb){ cb.checked = true; });
      applyFilters();
    });
    document.getElementById("deptNoneBtn").addEventListener("click", function(){
      document.querySelectorAll(".dept-checkbox").forEach(function(cb){ cb.checked = false; });
      applyFilters();
    });
  }

  /* ============================================================
     12. INICIO
     ============================================================ */
  function init(){
    renderDepartments();
    renderSideLegend();
    renderCityLabels();
    renderMarkers();
    buildFilterControls();
    wireFilterEvents();
    applyFilters();
  }

  init();
})();
</script>
</body>
</html>
