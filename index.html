<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>Lock Detector</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Teko:wght@400;600&display=swap');
  :root {
    --bg:#080c10;--surface:#0e1419;--border:#1e2d3d;
    --accent:#00d4ff;--green:#00ff9d;--red:#ff3b30;--yellow:#ffd60a;
    --text:#c8d6e5;--muted:#3d5166;
    --lock-col:#00d4ff;--noise-col:#ff6b35;
    --font-ui:'Share Tech Mono',monospace;--font-head:'Teko',sans-serif;
  }
  *{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
  body{background:var(--bg);color:var(--text);font-family:var(--font-ui);font-size:12px;
    min-height:100dvh;display:flex;flex-direction:column;padding:14px;gap:10px;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E")}
  header{display:flex;align-items:center;gap:10px;border-bottom:1px solid var(--border);padding-bottom:10px}
  .lock-icon{width:32px;height:32px;background:var(--accent);border-radius:6px;display:flex;
    align-items:center;justify-content:center;font-size:16px;flex-shrink:0;box-shadow:0 0 12px rgba(0,212,255,.4)}
  h1{font-family:var(--font-head);font-size:26px;font-weight:600;letter-spacing:2px;color:#fff;line-height:1}
  h1 span{color:var(--accent)}
  .version{margin-left:auto;color:var(--muted);font-size:10px;text-align:right;line-height:1.5}
  .status-bar{background:var(--surface);border:1px solid var(--border);border-radius:8px;
    padding:8px 12px;display:grid;grid-template-columns:1fr 1fr;gap:4px 16px;font-size:10px}
  .status-item{display:flex;justify-content:space-between;align-items:center}
  .status-item .key{color:var(--muted)}
  .status-item .val{color:var(--accent);font-weight:bold}
  .status-item .val.ok{color:var(--green)}
  .status-item .val.err{color:var(--red)}
  .status-item .val.warn{color:var(--yellow)}
  #btn{width:100%;padding:20px;font-family:var(--font-head);font-size:22px;font-weight:600;
    letter-spacing:3px;border:2px solid var(--border);border-radius:10px;
    background:var(--surface);color:var(--muted);cursor:not-allowed;transition:all .25s;position:relative;overflow:hidden}
  #btn.ready{border-color:var(--accent);color:var(--accent);cursor:pointer;
    box-shadow:0 0 20px rgba(0,212,255,.15),inset 0 0 20px rgba(0,212,255,.03)}
  #btn.recording{border-color:var(--red);color:var(--red);cursor:default;
    animation:pulse-border 1.6s ease-in-out infinite}
  @keyframes pulse-border{
    0%,100%{box-shadow:0 0 20px rgba(255,59,48,.2),inset 0 0 20px rgba(255,59,48,.05)}
    50%{box-shadow:0 0 35px rgba(255,59,48,.4),inset 0 0 30px rgba(255,59,48,.1)}}
  .meter-wrap{display:flex;align-items:center;gap:8px;font-size:10px;color:var(--muted)}
  .meter-bar{flex:1;height:5px;background:var(--border);border-radius:3px;overflow:hidden}
  .meter-fill{height:100%;width:0%;background:var(--green);border-radius:3px;transition:width .06s linear}
  .meter-fill.hot{background:var(--yellow)}
  .meter-fill.clip{background:var(--red)}
  .scores{display:grid;grid-template-columns:1fr 1fr;gap:8px}
  .score-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;
    padding:14px 12px 10px;text-align:center;transition:border-color .3s,box-shadow .3s;
    position:relative;overflow:hidden}
  .score-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;
    background:var(--border);transition:background .3s}
  .score-card.active-lock{border-color:var(--lock-col);box-shadow:0 0 18px rgba(0,212,255,.2)}
  .score-card.active-lock::after{background:var(--lock-col)}
  .score-card.active-noise{border-color:var(--noise-col);box-shadow:0 0 18px rgba(255,107,53,.2)}
  .score-card.active-noise::after{background:var(--noise-col)}
  .score-label{font-size:11px;letter-spacing:2px;color:var(--muted);margin-bottom:6px}
  .score-value{font-family:var(--font-head);font-size:42px;font-weight:600;line-height:1;
    color:var(--muted);transition:color .3s}
  .active-lock .score-value{color:var(--lock-col)}
  .active-noise .score-value{color:var(--noise-col)}
  .score-bar-wrap{margin-top:8px;height:3px;background:var(--border);border-radius:2px;overflow:hidden}
  .score-bar-fill{height:100%;width:0%;border-radius:2px;transition:width .3s ease}
  .card-lock .score-bar-fill{background:var(--lock-col)}
  .card-noise .score-bar-fill{background:var(--noise-col)}
  .verdict{text-align:center;padding:10px;border-radius:8px;font-family:var(--font-head);
    font-size:18px;font-weight:600;letter-spacing:3px;background:var(--surface);
    border:1px solid var(--border);color:var(--muted);transition:all .3s;
    min-height:46px;display:flex;align-items:center;justify-content:center;gap:8px}
  .verdict.lock{background:rgba(0,212,255,.08);border-color:var(--lock-col);color:var(--lock-col)}
  .verdict.noise{background:rgba(255,107,53,.08);border-color:var(--noise-col);color:var(--noise-col)}
  .log-header{display:flex;justify-content:space-between;align-items:center;
    color:var(--muted);font-size:10px;padding:0 2px}
  .log-clear{background:none;border:1px solid var(--border);color:var(--muted);
    font-family:var(--font-ui);font-size:10px;cursor:pointer;padding:2px 6px;border-radius:4px}
  #log{background:#050810;border:1px solid var(--border);border-radius:8px;height:200px;
    overflow-y:auto;padding:8px 10px;font-size:10px;line-height:1.7;flex:1}
  #log .l-ok{color:#3fb950}
  #log .l-warn{color:var(--yellow)}
  #log .l-err{color:var(--red)}
  #log .l-info{color:var(--muted)}
  #log .l-res{color:var(--accent)}
</style>
<script src="./edge-impulse-standalone.js?v=4"></script>
<script src="./run-impulse.js?v=4"></script>
</head>
<body>

<header>
  <div class="lock-icon">🔒</div>
  <div><h1>LOCK<span>SCAN</span></h1></div>
  <div class="version">Edge Impulse WASM<br>iPad Safari Fix v4</div>
</header>

<div class="status-bar">
  <div class="status-item"><span class="key">DEVICE SR</span><span class="val" id="s-device-sr">---</span></div>
  <div class="status-item"><span class="key">MODEL SR</span><span class="val" id="s-model-sr">---</span></div>
  <div class="status-item"><span class="key">INPUT SIZE</span><span class="val" id="s-input-size">---</span></div>
  <div class="status-item"><span class="key">ENGINE</span><span class="val" id="s-engine">LOADING</span></div>
</div>

<button id="btn" disabled onclick="startRecording()">LOADING ENGINE...</button>

<div class="meter-wrap">
  <span>IN</span>
  <div class="meter-bar"><div class="meter-fill" id="meter"></div></div>
  <span id="peak-val">0.000</span>
</div>

<div class="scores" id="score-cards"></div>
<div class="verdict" id="verdict">WAITING FOR INPUT</div>

<div class="log-header">
  <span>▸ SYSTEM LOG</span>
  <button class="log-clear" onclick="clearLog()">CLEAR</button>
</div>
<div id="log"></div>

<script>
'use strict';

const CFG = {
  MODEL_SR:    16000,
  WINDOW_SIZE: 16000,
  OVERLAP:     0.5,
  PROC_BUFFER: 4096,
  LOG_MAX:     150,
};

const EI_ERRORS = {
  '-1':'SHAPES_DONT_MATCH','-3':'TFLITE_ERROR','-5':'DSP_ERROR',
  '-6':'INVALID_SIZE','-7':'ALLOC_FAILED','-17':'INFERENCE_ERROR',
  '-23':'INPUT_SIGNAL_ERROR','-24':'SAMPLING_ERROR',
};

const $ = id => document.getElementById(id);
let logCount = 0;

function log(msg, cls='l-ok'){
  const box=$('log');
  const t=new Date().toLocaleTimeString('ja-JP',{hour12:false});
  const div=document.createElement('div');
  div.className=cls; div.textContent=`[${t}] ${msg}`;
  box.appendChild(div); box.scrollTop=box.scrollHeight;
  if(++logCount>CFG.LOG_MAX){box.removeChild(box.firstChild);logCount--;}
}

function clearLog(){$('log').innerHTML='';logCount=0;}

function setStat(id,val,cls=''){
  const el=$(id); el.textContent=val;
  el.className='val'+(cls?' '+cls:'');
}

function resample(input,fromSR,toSR){
  if(fromSR===toSR) return new Float32Array(input);
  const ratio=fromSR/toSR;
  const outLen=Math.round(input.length/ratio);
  const out=new Float32Array(outLen);
  for(let i=0;i<outLen;i++){
    const pos=i*ratio, idx=Math.floor(pos), frac=pos-idx;
    out[i]=(idx+1<input.length)
      ?input[idx]*(1-frac)+input[idx+1]*frac
      :input[idx];
  }
  return out;
}

let classifier=null, actualSR=CFG.MODEL_SR, modelInputSize=CFG.WINDOW_SIZE;
let sampleBuf=[], isClassifying=false, isRecording=false, knownLabels=[];

function labelClass(label){
  const u=label.toUpperCase();
  if(u.includes('LOCK'))  return 'lock';
  if(u.includes('NOISE')) return 'noise';
  return 'other';
}

function buildScoreCards(labels){
  knownLabels=labels;
  $('score-cards').innerHTML=labels.map(label=>{
    const lc=labelClass(label);
    return `<div class="score-card card-${lc}" id="card-${label}">
      <div class="score-label">${label}</div>
      <div class="score-value" id="val-${label}">--%</div>
      <div class="score-bar-wrap"><div class="score-bar-fill" id="bar-${label}"></div></div>
    </div>`;
  }).join('');
}

function updateCards(results){
  const winner=results.reduce((a,b)=>a.value>b.value?a:b);
  results.forEach(r=>{
    const pct=(r.value*100).toFixed(1);
    const valEl=$(`val-${r.label}`);
    const barEl=$(`bar-${r.label}`);
    const card=$(`card-${r.label}`);
    if(!valEl) return;
    valEl.textContent=pct+'%';
    barEl.style.width=pct+'%';
    card.classList.remove('active-lock','active-noise');
    if(r.label===winner.label){
      card.classList.add(labelClass(r.label)==='lock'?'active-lock':'active-noise');
    }
  });
  const verdict=$('verdict');
  const wlc=labelClass(winner.label);
  verdict.className='verdict '+wlc;
  verdict.innerHTML=(wlc==='lock'?'🔒':'🔊')+' '+winner.label
    +` <small style="font-size:14px;opacity:.7">${(winner.value*100).toFixed(1)}%</small>`;
}

window.addEventListener('load', async()=>{
  log('▶ EdgeImpulseClassifier 初期化開始...');
  try{
    classifier=new EdgeImpulseClassifier();
    await classifier.init();
    let props={};
    if(typeof classifier.getProperties==='function') props=classifier.getProperties();
    log('✅ 初期化成功');
    log('props='+JSON.stringify(props),'l-info');

    modelInputSize=props.inputSize??props.signal_length??props.frame_sample_count??CFG.WINDOW_SIZE;
    const modelSR=props.frequency??props.sampleRate??CFG.MODEL_SR;

    setStat('s-model-sr',   modelSR,        'ok');
    setStat('s-input-size', modelInputSize,  'ok');
    setStat('s-engine',     'READY',         'ok');

    const labels=props.labels??props.model_output_names??[];
    if(labels.length>0){buildScoreCards(labels);log('ラベル: '+labels.join(' / '),'l-info');}

    const btn=$('btn');
    btn.disabled=false; btn.textContent='▶  START RECORDING'; btn.className='ready';
  }catch(e){
    log('❌ 初期化失敗: '+e.message,'l-err');
    setStat('s-engine','ERROR','err');
  }
});

async function startRecording(){
  if(isRecording||!classifier) return;
  const btn=$('btn');
  btn.disabled=true;
  try{
    log('▶ AudioContext 作成中...');
    // Fix1: sampleRate指定しない（Safariは無視するため実測してリサンプル）
    const audioCtx=new (window.AudioContext||window.webkitAudioContext)();
    // Fix2: suspended対策
    if(audioCtx.state==='suspended'){await audioCtx.resume();log('AudioContext resume()完了','l-info');}

    actualSR=audioCtx.sampleRate;
    setStat('s-device-sr',actualSR,actualSR===CFG.MODEL_SR?'ok':'warn');
    log(`AudioContext SR: ${actualSR} Hz（モデル要求: ${CFG.MODEL_SR} Hz）`);
    if(actualSR!==CFG.MODEL_SR) log(`⚠ SRミスマッチ → リサンプリング有効 (${actualSR}→${CFG.MODEL_SR})`,'l-warn');

    // Fix3: getUserMedia制約は最小限
    const stream=await navigator.mediaDevices.getUserMedia({audio:true});
    log('✅ マイクアクセス成功');

    const source=audioCtx.createMediaStreamSource(stream);
    const processor=audioCtx.createScriptProcessor(CFG.PROC_BUFFER,1,1);
    const targetSamples=Math.round(modelInputSize*actualSR/CFG.MODEL_SR);
    const slideStep=Math.round(targetSamples*(1-CFG.OVERLAP));
    log(`バッファ目標: ${targetSamples} smp / スライド: ${slideStep} smp`,'l-info');

    processor.onaudioprocess=(e)=>{
      const chunk=e.inputBuffer.getChannelData(0);
      let peak=0;
      for(let i=0;i<chunk.length;i++){const a=Math.abs(chunk[i]);if(a>peak)peak=a;}
      const pct=Math.min(100,peak*200);
      const fill=$('meter');
      fill.style.width=pct+'%';
      fill.className='meter-fill'+(pct>90?' clip':pct>65?' hot':'');
      $('peak-val').textContent=peak.toFixed(3);

      for(let i=0;i<chunk.length;i++) sampleBuf.push(chunk[i]);

      if(sampleBuf.length>=targetSamples&&!isClassifying){
        const win=new Float32Array(sampleBuf.slice(0,targetSamples));
        sampleBuf=sampleBuf.slice(slideStep);
        // Fix4: オーディオスレッドから切り離す
        setTimeout(()=>runInference(win),0);
      }
    };

    source.connect(processor);
    processor.connect(audioCtx.destination);
    isRecording=true;
    btn.textContent='⏺  RECORDING...'; btn.className='recording';
    log('🎤 監視開始');
  }catch(e){
    log('❌ 録音エラー: '+e.message,'l-err');
    btn.disabled=false; btn.textContent='▶  RETRY'; btn.className='ready';
  }
}

async function runInference(rawChunk){
  isClassifying=true;
  try{
    const resampled=resample(rawChunk,actualSR,CFG.MODEL_SR);
    const peak=Math.max(...resampled.map(Math.abs));
    if(peak<0.001){log('⚠ ほぼ無音','l-warn');return;}

    // Fix5（核心）: TypedArray→通常JS Arrayに変換
    // Float32Array/Int16ArrayのままだとWASMシグナルコールバックがerr-24を返す
    const inputArray=Array.from(resampled);
    log(`classify() [${inputArray.length} smp, peak=${peak.toFixed(4)}]`,'l-info');

    let res;
    try{
      res=classifier.classify(inputArray);          // パターンA: 同期
    }catch(e1){
      log('パターンA失敗: '+e1.message,'l-warn');
      try{
        res=await Promise.resolve(classifier.classify(inputArray)); // パターンB: async
      }catch(e2){
        log('パターンB失敗: '+e2.message,'l-warn');
        res=classifier.classify(inputArray,true);   // パターンC: debug=true
      }
    }

    log('RAW: '+JSON.stringify(res),'l-info');

    let results=null;
    if(Array.isArray(res?.results)){
      results=res.results.map(r=>({label:r.label,value:r.value}));
    }else if(res?.classification&&typeof res.classification==='object'){
      results=Object.entries(res.classification).map(([label,value])=>({label,value}));
    }else if(typeof res==='object'&&res!==null){
      const flat=Object.entries(res).filter(([,v])=>typeof v==='number').map(([label,value])=>({label,value}));
      if(flat.length>0) results=flat;
    }

    if(!results||results.length===0){log('⚠ 結果形式を解析できません: '+JSON.stringify(res),'l-warn');return;}

    if(knownLabels.length===0) buildScoreCards(results.map(r=>r.label));
    updateCards(results);

    results.sort((a,b)=>b.value-a.value);
    results.forEach(r=>{
      const bar='█'.repeat(Math.round(r.value*20)).padEnd(20,'░');
      log(`  ${r.label.padEnd(8)} ${(r.value*100).toFixed(1).padStart(5)}% |${bar}|`,'l-res');
    });

  }catch(e){
    const code=(e.message.match(/-?\d+/)??['?'])[0];
    const desc=EI_ERRORS[code]??'不明';
    log(`❌ 推論エラー [code:${code}=${desc}] ${e.message}`,'l-err');
    if(code==='-24') log('→ コンソールで window.__dbg() を実行して結果を共有してください','l-warn');
  }finally{
    isClassifying=false;
  }
}

// デバッグ用: Safari Web Inspector コンソールで window.__dbg() を実行
window.__dbg=()=>{
  if(!classifier){console.warn('classifier未初期化');return;}
  console.group('EI Debug');
  console.log('getProperties:',classifier.getProperties?.());
  console.log('classify src:',classifier.classify.toString());
  console.groupEnd();
};
</script>
</body>
</html>
