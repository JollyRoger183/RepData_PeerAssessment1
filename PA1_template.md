<!DOCTYPE html>
<!-- saved from url=(0014)about:internet -->
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
<meta http-equiv="x-ua-compatible" content="IE=9" >

<title>Reproducible Research - Programming Assignment 1</title>

<style type="text/css">
body, td {
   font-family: sans-serif;
   background-color: white;
   font-size: 12px;
   margin: 8px;
}

tt, code, pre {
   font-family: 'DejaVu Sans Mono', 'Droid Sans Mono', 'Lucida Console', Consolas, Monaco, monospace;
}

h1 { 
   font-size:2.2em; 
}

h2 { 
   font-size:1.8em; 
}

h3 { 
   font-size:1.4em; 
}

h4 { 
   font-size:1.0em; 
}

h5 { 
   font-size:0.9em; 
}

h6 { 
   font-size:0.8em; 
}

a:visited {
   color: rgb(50%, 0%, 50%);
}

pre {	
   margin-top: 0;
   max-width: 95%;
   border: 1px solid #ccc;
   white-space: pre-wrap;
}

pre code {
   display: block; padding: 0.5em;
}

code.r, code.cpp {
   background-color: #F8F8F8;
}

table, td, th {
  border: none;
}

blockquote {
   color:#666666;
   margin:0;
   padding-left: 1em;
   border-left: 0.5em #EEE solid;
}

hr {
   height: 0px;
   border-bottom: none;
   border-top-width: thin;
   border-top-style: dotted;
   border-top-color: #999999;
}

@media print {
   * { 
      background: transparent !important; 
      color: black !important; 
      filter:none !important; 
      -ms-filter: none !important; 
   }

   body { 
      font-size:12pt; 
      max-width:100%; 
   }
       
   a, a:visited { 
      text-decoration: underline; 
   }

   hr { 
      visibility: hidden;
      page-break-before: always;
   }

   pre, blockquote { 
      padding-right: 1em; 
      page-break-inside: avoid; 
   }

   tr, img { 
      page-break-inside: avoid; 
   }

   img { 
      max-width: 100% !important; 
   }

   @page :left { 
      margin: 15mm 20mm 15mm 10mm; 
   }
     
   @page :right { 
      margin: 15mm 10mm 15mm 20mm; 
   }

   p, h2, h3 { 
      orphans: 3; widows: 3; 
   }

   h2, h3 { 
      page-break-after: avoid; 
   }
}

</style>

<!-- Styles for R syntax highlighter -->
<style type="text/css">
   pre .operator,
   pre .paren {
     color: rgb(104, 118, 135)
   }

   pre .literal {
     color: rgb(88, 72, 246)
   }

   pre .number {
     color: rgb(0, 0, 205);
   }

   pre .comment {
     color: rgb(76, 136, 107);
   }

   pre .keyword {
     color: rgb(0, 0, 255);
   }

   pre .identifier {
     color: rgb(0, 0, 0);
   }

   pre .string {
     color: rgb(3, 106, 7);
   }
</style>

<!-- R syntax highlighter -->
<script type="text/javascript">
var hljs=new function(){function m(p){return p.replace(/&/gm,"&amp;").replace(/</gm,"&lt;")}function f(r,q,p){return RegExp(q,"m"+(r.cI?"i":"")+(p?"g":""))}function b(r){for(var p=0;p<r.childNodes.length;p++){var q=r.childNodes[p];if(q.nodeName=="CODE"){return q}if(!(q.nodeType==3&&q.nodeValue.match(/\s+/))){break}}}function h(t,s){var p="";for(var r=0;r<t.childNodes.length;r++){if(t.childNodes[r].nodeType==3){var q=t.childNodes[r].nodeValue;if(s){q=q.replace(/\n/g,"")}p+=q}else{if(t.childNodes[r].nodeName=="BR"){p+="\n"}else{p+=h(t.childNodes[r])}}}if(/MSIE [678]/.test(navigator.userAgent)){p=p.replace(/\r/g,"\n")}return p}function a(s){var r=s.className.split(/\s+/);r=r.concat(s.parentNode.className.split(/\s+/));for(var q=0;q<r.length;q++){var p=r[q].replace(/^language-/,"");if(e[p]){return p}}}function c(q){var p=[];(function(s,t){for(var r=0;r<s.childNodes.length;r++){if(s.childNodes[r].nodeType==3){t+=s.childNodes[r].nodeValue.length}else{if(s.childNodes[r].nodeName=="BR"){t+=1}else{if(s.childNodes[r].nodeType==1){p.push({event:"start",offset:t,node:s.childNodes[r]});t=arguments.callee(s.childNodes[r],t);p.push({event:"stop",offset:t,node:s.childNodes[r]})}}}}return t})(q,0);return p}function k(y,w,x){var q=0;var z="";var s=[];function u(){if(y.length&&w.length){if(y[0].offset!=w[0].offset){return(y[0].offset<w[0].offset)?y:w}else{return w[0].event=="start"?y:w}}else{return y.length?y:w}}function t(D){var A="<"+D.nodeName.toLowerCase();for(var B=0;B<D.attributes.length;B++){var C=D.attributes[B];A+=" "+C.nodeName.toLowerCase();if(C.value!==undefined&&C.value!==false&&C.value!==null){A+='="'+m(C.value)+'"'}}return A+">"}while(y.length||w.length){var v=u().splice(0,1)[0];z+=m(x.substr(q,v.offset-q));q=v.offset;if(v.event=="start"){z+=t(v.node);s.push(v.node)}else{if(v.event=="stop"){var p,r=s.length;do{r--;p=s[r];z+=("</"+p.nodeName.toLowerCase()+">")}while(p!=v.node);s.splice(r,1);while(r<s.length){z+=t(s[r]);r++}}}}return z+m(x.substr(q))}function j(){function q(x,y,v){if(x.compiled){return}var u;var s=[];if(x.k){x.lR=f(y,x.l||hljs.IR,true);for(var w in x.k){if(!x.k.hasOwnProperty(w)){continue}if(x.k[w] instanceof Object){u=x.k[w]}else{u=x.k;w="keyword"}for(var r in u){if(!u.hasOwnProperty(r)){continue}x.k[r]=[w,u[r]];s.push(r)}}}if(!v){if(x.bWK){x.b="\\b("+s.join("|")+")\\s"}x.bR=f(y,x.b?x.b:"\\B|\\b");if(!x.e&&!x.eW){x.e="\\B|\\b"}if(x.e){x.eR=f(y,x.e)}}if(x.i){x.iR=f(y,x.i)}if(x.r===undefined){x.r=1}if(!x.c){x.c=[]}x.compiled=true;for(var t=0;t<x.c.length;t++){if(x.c[t]=="self"){x.c[t]=x}q(x.c[t],y,false)}if(x.starts){q(x.starts,y,false)}}for(var p in e){if(!e.hasOwnProperty(p)){continue}q(e[p].dM,e[p],true)}}function d(B,C){if(!j.called){j();j.called=true}function q(r,M){for(var L=0;L<M.c.length;L++){if((M.c[L].bR.exec(r)||[null])[0]==r){return M.c[L]}}}function v(L,r){if(D[L].e&&D[L].eR.test(r)){return 1}if(D[L].eW){var M=v(L-1,r);return M?M+1:0}return 0}function w(r,L){return L.i&&L.iR.test(r)}function K(N,O){var M=[];for(var L=0;L<N.c.length;L++){M.push(N.c[L].b)}var r=D.length-1;do{if(D[r].e){M.push(D[r].e)}r--}while(D[r+1].eW);if(N.i){M.push(N.i)}return f(O,M.join("|"),true)}function p(M,L){var N=D[D.length-1];if(!N.t){N.t=K(N,E)}N.t.lastIndex=L;var r=N.t.exec(M);return r?[M.substr(L,r.index-L),r[0],false]:[M.substr(L),"",true]}function z(N,r){var L=E.cI?r[0].toLowerCase():r[0];var M=N.k[L];if(M&&M instanceof Array){return M}return false}function F(L,P){L=m(L);if(!P.k){return L}var r="";var O=0;P.lR.lastIndex=0;var M=P.lR.exec(L);while(M){r+=L.substr(O,M.index-O);var N=z(P,M);if(N){x+=N[1];r+='<span class="'+N[0]+'">'+M[0]+"</span>"}else{r+=M[0]}O=P.lR.lastIndex;M=P.lR.exec(L)}return r+L.substr(O,L.length-O)}function J(L,M){if(M.sL&&e[M.sL]){var r=d(M.sL,L);x+=r.keyword_count;return r.value}else{return F(L,M)}}function I(M,r){var L=M.cN?'<span class="'+M.cN+'">':"";if(M.rB){y+=L;M.buffer=""}else{if(M.eB){y+=m(r)+L;M.buffer=""}else{y+=L;M.buffer=r}}D.push(M);A+=M.r}function G(N,M,Q){var R=D[D.length-1];if(Q){y+=J(R.buffer+N,R);return false}var P=q(M,R);if(P){y+=J(R.buffer+N,R);I(P,M);return P.rB}var L=v(D.length-1,M);if(L){var O=R.cN?"</span>":"";if(R.rE){y+=J(R.buffer+N,R)+O}else{if(R.eE){y+=J(R.buffer+N,R)+O+m(M)}else{y+=J(R.buffer+N+M,R)+O}}while(L>1){O=D[D.length-2].cN?"</span>":"";y+=O;L--;D.length--}var r=D[D.length-1];D.length--;D[D.length-1].buffer="";if(r.starts){I(r.starts,"")}return R.rE}if(w(M,R)){throw"Illegal"}}var E=e[B];var D=[E.dM];var A=0;var x=0;var y="";try{var s,u=0;E.dM.buffer="";do{s=p(C,u);var t=G(s[0],s[1],s[2]);u+=s[0].length;if(!t){u+=s[1].length}}while(!s[2]);if(D.length>1){throw"Illegal"}return{r:A,keyword_count:x,value:y}}catch(H){if(H=="Illegal"){return{r:0,keyword_count:0,value:m(C)}}else{throw H}}}function g(t){var p={keyword_count:0,r:0,value:m(t)};var r=p;for(var q in e){if(!e.hasOwnProperty(q)){continue}var s=d(q,t);s.language=q;if(s.keyword_count+s.r>r.keyword_count+r.r){r=s}if(s.keyword_count+s.r>p.keyword_count+p.r){r=p;p=s}}if(r.language){p.second_best=r}return p}function i(r,q,p){if(q){r=r.replace(/^((<[^>]+>|\t)+)/gm,function(t,w,v,u){return w.replace(/\t/g,q)})}if(p){r=r.replace(/\n/g,"<br>")}return r}function n(t,w,r){var x=h(t,r);var v=a(t);var y,s;if(v){y=d(v,x)}else{return}var q=c(t);if(q.length){s=document.createElement("pre");s.innerHTML=y.value;y.value=k(q,c(s),x)}y.value=i(y.value,w,r);var u=t.className;if(!u.match("(\\s|^)(language-)?"+v+"(\\s|$)")){u=u?(u+" "+v):v}if(/MSIE [678]/.test(navigator.userAgent)&&t.tagName=="CODE"&&t.parentNode.tagName=="PRE"){s=t.parentNode;var p=document.createElement("div");p.innerHTML="<pre><code>"+y.value+"</code></pre>";t=p.firstChild.firstChild;p.firstChild.cN=s.cN;s.parentNode.replaceChild(p.firstChild,s)}else{t.innerHTML=y.value}t.className=u;t.result={language:v,kw:y.keyword_count,re:y.r};if(y.second_best){t.second_best={language:y.second_best.language,kw:y.second_best.keyword_count,re:y.second_best.r}}}function o(){if(o.called){return}o.called=true;var r=document.getElementsByTagName("pre");for(var p=0;p<r.length;p++){var q=b(r[p]);if(q){n(q,hljs.tabReplace)}}}function l(){if(window.addEventListener){window.addEventListener("DOMContentLoaded",o,false);window.addEventListener("load",o,false)}else{if(window.attachEvent){window.attachEvent("onload",o)}else{window.onload=o}}}var e={};this.LANGUAGES=e;this.highlight=d;this.highlightAuto=g;this.fixMarkup=i;this.highlightBlock=n;this.initHighlighting=o;this.initHighlightingOnLoad=l;this.IR="[a-zA-Z][a-zA-Z0-9_]*";this.UIR="[a-zA-Z_][a-zA-Z0-9_]*";this.NR="\\b\\d+(\\.\\d+)?";this.CNR="\\b(0[xX][a-fA-F0-9]+|(\\d+(\\.\\d*)?|\\.\\d+)([eE][-+]?\\d+)?)";this.BNR="\\b(0b[01]+)";this.RSR="!|!=|!==|%|%=|&|&&|&=|\\*|\\*=|\\+|\\+=|,|\\.|-|-=|/|/=|:|;|<|<<|<<=|<=|=|==|===|>|>=|>>|>>=|>>>|>>>=|\\?|\\[|\\{|\\(|\\^|\\^=|\\||\\|=|\\|\\||~";this.ER="(?![\\s\\S])";this.BE={b:"\\\\.",r:0};this.ASM={cN:"string",b:"'",e:"'",i:"\\n",c:[this.BE],r:0};this.QSM={cN:"string",b:'"',e:'"',i:"\\n",c:[this.BE],r:0};this.CLCM={cN:"comment",b:"//",e:"$"};this.CBLCLM={cN:"comment",b:"/\\*",e:"\\*/"};this.HCM={cN:"comment",b:"#",e:"$"};this.NM={cN:"number",b:this.NR,r:0};this.CNM={cN:"number",b:this.CNR,r:0};this.BNM={cN:"number",b:this.BNR,r:0};this.inherit=function(r,s){var p={};for(var q in r){p[q]=r[q]}if(s){for(var q in s){p[q]=s[q]}}return p}}();hljs.LANGUAGES.cpp=function(){var a={keyword:{"false":1,"int":1,"float":1,"while":1,"private":1,"char":1,"catch":1,"export":1,virtual:1,operator:2,sizeof:2,dynamic_cast:2,typedef:2,const_cast:2,"const":1,struct:1,"for":1,static_cast:2,union:1,namespace:1,unsigned:1,"long":1,"throw":1,"volatile":2,"static":1,"protected":1,bool:1,template:1,mutable:1,"if":1,"public":1,friend:2,"do":1,"return":1,"goto":1,auto:1,"void":2,"enum":1,"else":1,"break":1,"new":1,extern:1,using:1,"true":1,"class":1,asm:1,"case":1,typeid:1,"short":1,reinterpret_cast:2,"default":1,"double":1,register:1,explicit:1,signed:1,typename:1,"try":1,"this":1,"switch":1,"continue":1,wchar_t:1,inline:1,"delete":1,alignof:1,char16_t:1,char32_t:1,constexpr:1,decltype:1,noexcept:1,nullptr:1,static_assert:1,thread_local:1,restrict:1,_Bool:1,complex:1},built_in:{std:1,string:1,cin:1,cout:1,cerr:1,clog:1,stringstream:1,istringstream:1,ostringstream:1,auto_ptr:1,deque:1,list:1,queue:1,stack:1,vector:1,map:1,set:1,bitset:1,multiset:1,multimap:1,unordered_set:1,unordered_map:1,unordered_multiset:1,unordered_multimap:1,array:1,shared_ptr:1}};return{dM:{k:a,i:"</",c:[hljs.CLCM,hljs.CBLCLM,hljs.QSM,{cN:"string",b:"'\\\\?.",e:"'",i:"."},{cN:"number",b:"\\b(\\d+(\\.\\d*)?|\\.\\d+)(u|U|l|L|ul|UL|f|F)"},hljs.CNM,{cN:"preprocessor",b:"#",e:"$"},{cN:"stl_container",b:"\\b(deque|list|queue|stack|vector|map|set|bitset|multiset|multimap|unordered_map|unordered_set|unordered_multiset|unordered_multimap|array)\\s*<",e:">",k:a,r:10,c:["self"]}]}}}();hljs.LANGUAGES.r={dM:{c:[hljs.HCM,{cN:"number",b:"\\b0[xX][0-9a-fA-F]+[Li]?\\b",e:hljs.IMMEDIATE_RE,r:0},{cN:"number",b:"\\b\\d+(?:[eE][+\\-]?\\d*)?L\\b",e:hljs.IMMEDIATE_RE,r:0},{cN:"number",b:"\\b\\d+\\.(?!\\d)(?:i\\b)?",e:hljs.IMMEDIATE_RE,r:1},{cN:"number",b:"\\b\\d+(?:\\.\\d*)?(?:[eE][+\\-]?\\d*)?i?\\b",e:hljs.IMMEDIATE_RE,r:0},{cN:"number",b:"\\.\\d+(?:[eE][+\\-]?\\d*)?i?\\b",e:hljs.IMMEDIATE_RE,r:1},{cN:"keyword",b:"(?:tryCatch|library|setGeneric|setGroupGeneric)\\b",e:hljs.IMMEDIATE_RE,r:10},{cN:"keyword",b:"\\.\\.\\.",e:hljs.IMMEDIATE_RE,r:10},{cN:"keyword",b:"\\.\\.\\d+(?![\\w.])",e:hljs.IMMEDIATE_RE,r:10},{cN:"keyword",b:"\\b(?:function)",e:hljs.IMMEDIATE_RE,r:2},{cN:"keyword",b:"(?:if|in|break|next|repeat|else|for|return|switch|while|try|stop|warning|require|attach|detach|source|setMethod|setClass)\\b",e:hljs.IMMEDIATE_RE,r:1},{cN:"literal",b:"(?:NA|NA_integer_|NA_real_|NA_character_|NA_complex_)\\b",e:hljs.IMMEDIATE_RE,r:10},{cN:"literal",b:"(?:NULL|TRUE|FALSE|T|F|Inf|NaN)\\b",e:hljs.IMMEDIATE_RE,r:1},{cN:"identifier",b:"[a-zA-Z.][a-zA-Z0-9._]*\\b",e:hljs.IMMEDIATE_RE,r:0},{cN:"operator",b:"<\\-(?!\\s*\\d)",e:hljs.IMMEDIATE_RE,r:2},{cN:"operator",b:"\\->|<\\-",e:hljs.IMMEDIATE_RE,r:1},{cN:"operator",b:"%%|~",e:hljs.IMMEDIATE_RE},{cN:"operator",b:">=|<=|==|!=|\\|\\||&&|=|\\+|\\-|\\*|/|\\^|>|<|!|&|\\||\\$|:",e:hljs.IMMEDIATE_RE,r:0},{cN:"operator",b:"%",e:"%",i:"\\n",r:1},{cN:"identifier",b:"`",e:"`",r:0},{cN:"string",b:'"',e:'"',c:[hljs.BE],r:0},{cN:"string",b:"'",e:"'",c:[hljs.BE],r:0},{cN:"paren",b:"[[({\\])}]",e:hljs.IMMEDIATE_RE,r:0}]}};
hljs.initHighlightingOnLoad();
</script>




</head>

<body>
<h1>Reproducible Research - Programming Assignment 1</h1>

<h2>Loading and preprocessing the data</h2>

<pre><code class="r">setwd(&quot;C:\\02_LEARNING\\coursera\\Data Science\\06 - Reproducible Research\\Assignment1&quot;)

xdata &lt;- read.csv(file = &quot;activity.csv&quot;, header = TRUE)
</code></pre>

<h2>What is mean total number of steps taken per day?</h2>

<pre><code class="r">sum_steps_daily &lt;- aggregate(x = xdata$steps, by = list(xdata$date), FUN = sum)
</code></pre>

<p>The mean total number of steps taken per day is: 1.0766 &times; 10<sup>4</sup>.
With a median of 10765 steps taken per day.</p>

<p>The data can be summarized with the following histogram:</p>

<pre><code class="r">hist(sum_steps_daily$x, breaks = 20, col = &quot;grey&quot;, ylim = c(0, 11), main = &quot;Histogram of steps per day&quot;, 
    las = 1, xlab = &quot;Steps per day&quot;)

abline(abline(v = mean(sum_steps_daily$x, na.rm = T), col = &quot;red&quot;))
text(x = mean(sum_steps_daily$x, na.rm = T), y = 11, labels = &quot;Mean&quot;)
</code></pre>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAAGwCAMAAABy/YdMAAAAulBMVEX9/v0AAAAAADkAAGUAOTkAOWUAOY8AZo8AZrU5AAA5ADk5AGU5OWU5OY85Zo85ZrU5j485j9plAABlADllAGVlOQBlOTllOY9lZjllZmVlZrVltbVltf2POQCPOTmPOWWPZgCPZo+PjzmPj2WPtY+P27WP29qP2/2QAAC1ZgC1Zjm1tWW124+1/rW1/tq1/v22AAC+vr7ajznaj2Xa/rXa/tra/v3bAAD9tWX924/9/rX9/tr9/v3/AABfsc/RAAAAPnRSTlP///////////////////////////////////////////////////////////////////////////////8A/wTdY8kAAAAJcEhZcwAACxIAAAsSAdLdfvwAAA7WSURBVHic7Z0Be6PGEUCL3Vytu6SpdXdN0qJL2iZ1laR1o6aukPD//1tlFpAtgQWMkLzDvPd9F1nLatmdp90FhYXf5OCS37x2BeB1QLxTEO8UxDsF8U5BvFMQ7xTEOwXxTkG8UxDvFMQ7BfFOQbxTEO8UxDsF8U5BvFMQ7xTEOwXxTkG8UxDvFMQ7BfFOMSV+M7++z/Pt4vq+/KtmmZ5QaDZLru72Uk4qLrCZv3k4tYwzY1T8XvIySU8otPHp04oLIH5cDnp80VeT6/vtIkmSmzxfFS+3uWxOrv9ZBH67uPq66MvrIrno0evkd0X6fZEprQor84dPl5aaxaVhZz9Jcr05fPQp8Slb2Fm5MUn+LOLLPYev6TrULCoMi9/ME5H239LUUt4Ur0Hcb2ciXrb+WmZ6WCc1lbwq/5P4tuKqL4bkqDaHr8gucT9b2Nj4wKr4YiwPJpMIMCa+difis1k1nsrYnM2K2G7mV3fZrDC7SoL4m/pj1/frRD6QpJJF0nb5dyP7QXHFG/mGFaXcyn7T3eY8yH2WWGWrdrbbf73nbHbTmJwiwLD48E4iKqbWIfBF7wp/bMqh/q7+kIi/CRrq1F3+nfiD4gLVSF3ku91tzuujjCLxWba6T+/2X+95uyiGnZuLx6oLY+Ibc3xS9dmXxIc8O/FPX4em+IPiDsXvNuc9xdd7zldX38+im+JNixeWlbq2oV5clMqa4ptD/UFx1cC+G9V3m/PDob5MqcXv9l/vueV8MQYMi991qeULB3cS7nXS3uN3+Z/N8c3iqkNE+WO3OW8e3D0r9mlbvWdJifDkzrD4oKoazovI1qdzRU+sT+fERaHmtpoB9sTv8u8N9U/FLUuz5ZmbiKs35/mzxKdsu04t5v8wL0uQPUue+KZ4W+J7sx6tj7UekA88Sl+d/ovQ+ExOfHXkP9bR1AjiYzyZm6D4clYfbWw9XfyzHwtjYnrioReIdwrinYJ4pyDeKYh3CuKdgninIN4piHcK4p2CeKcg3imIdwrinYJ4pyDeKYh3CuKdgninID7w+NoVuDiIDyDeKYh3CuKdgninIN4piHcK4r2QzWRd5bJe/Ih4L2Rvf/+Qb/74DvHOyN59fZdn3xTi5Q4a94/hhhdpnn3xXZyrmkfHr/if0vw/3xfil7f56uZx8774Hry7z2a3+TrCO9aMj1/xP3+5/fbnd/difPPh35K2+XBfuBf/r127C+BX/L/+8uufCsfh1ilX/wi3MbpG/OQp7P74t1sR/0E0P27maRjqET9xCrvrq7usnOPXb/4XjL+9Q/zUKXt3Vh7VX909yj2KPvuYIt4ZnMc7BfFOQbxTEO8UxDsF8U5BvFMQ7xTEOwXxTkG8UxDvFMQ7BfFOQbxTEN8kXJewmcf4tMTxQHyDdfmUzDRfRfi4xNFA/CHLK7n2XK5InPQVSYhvEi5D++IhlwvQS5Ka81btvCR7PFpvzmD6iZfFJU/ia0xHKvnlOY/FP9PNGYymx9eYjhTiu8henONNRwrxXYjw7eK25ajedKQQ38XL5/GmI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOFeD2mI4V4PaYjhXg9piOF+F5kM3lewQGmI4X4Psidq1eNe5qajhTi+xBuW/6Bu1dPCE2Pn8YTKhDfB+5ePTV6DvVv7/J14+jOdKQQ3weeSTM56PGIP8Y6Sa4OOzziLcMvd4gfjOlIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV6P6UghXo/pSCFej+lIIV7YzG8UnzUdKcSXtK6D7sB0pBC/Y7tIknTIZ01HCvEl2Ux6fPOWZscwHSnEC5t5855W3ZiOFOL1mI4U4gPrYnZfDT26Mx0pxAvlrcyyd0NmeMSbphS/XaR5eTe7IZiOFOIDm3mStNyY/DimI4V4PaYjhXg9piOF+MA63IZ84FhvOlKIFzbz9Hi27YJbmk6LSnzXT7XLtOWY33SkEB9Y3h7N1f7FMB0pxAvhbO7IHJ998d2zoX6qjybpwWvXejx63q9+loYHEu1jOgwt4n85oJEwpUFhwFOoJv+ECo/ii6P2N782zO7YfIX4SYrfLm6LTn3kt/olQ/0kxRdH7YXXIyd1xdHf9B8x6lB82eObDxE9jukwID4gF1q2PFLwOKbDgHg9psOAeD2mw4B4oeuXu3ZMhwHxT6yO/2DfwHQYEP/EsOUUiDfNc/HNp8cex3QYEC9Uc3w67LOmw4B4PabDgHg9psOAeKEa6gee0JkOA+IDq5v6PwMwHQbEC+WJHKdz7sRvF/LbDT3enfjy/84NvQGS6TAgXo/pMCBej+kwID7QcbFlO6bDgHih82LLViIOQ/dSiHOJt7IIo+fFlq1E2iShKfF4jhHFGxklJnqxJeK7mOjFlojvYqJH9Yjvouf6+FYibZKA+C6qOf7T0DtXC5E2SUB8FxO9yhbxXTDHI34wkTZJQHwXIl53aId45Z7joBbfXP3eTaRNEhDfBeIRP/izkTZJQHwXQbzqGlvEK/ccBxzVI34wkTZJQHwXiEf8YCJtkoD4LhCP+MFE2iQB8V0gHvHHKZ9QtkekTRIQ30Vv8avm/TIibZKA+C76is8+/5gepkXaJAHxXfQUv/3090Vav4l8qYBwLvHdqyUmJn51yxzfmkWx5zjo/YQKxHsUvwrD2uGNLyNtkoD4LjidQ/xxEO9UfAuRNklAfBeIR/xgIm2SgPguEI/4wUTaJAHxXSAe8YOJtEkC4rtAPOIHE2mTBMR3gXjEDybSJgmI7wLxiB9MpE0SEN8F4hE/mEibJCC+C8QjfjCRNklAfBeIR/xgIm2SgPguEI/4wUTaJAHxXSAe8YOJtEkC4rtAPOIHE2mTBMR3gXjEDybSJgmI7wLxiB9MpE0SEN8F4hE/mEibJCC+C8QjfjCRNklAfBeIR/xgIm2SgPguEI/4wUTaJAHxXSAe8YOJtEkC4rtAPOIHE2mTBMR3gXjEHyObJTyhwqH4zfu7PHt7d5AaaZMExHfRT/z6pvjPMj1IjbRJAuK76D/HS68veeG5HD2e26GhWWxTYpNG+I/nUIvvsedRojA6A25bfvicgsMef6Ymt4S/R5aBCWrxPbKMEoXR6St+M294R7wD8dksbSYifvLiW70jfvriy4cRpQepiJ+8+HYQj/jw9jxNRvxZQHwA8UNAPOLD2/M0GfFnAfEBxA8B8YgPb8/TZMSfBcQHED8ExCM+vD1PkxF/FhAfQPwQEI/48PY8TUb8WUB8APFDQDziw9vzNBnxZwHxAcQPAfGID2+7m9yy/qCbZmx7ZBmYcFHxzfr3iHUPBsm7sPgzxVaR5TXFd2dRRW6QPMQHED8ExCO+vW6q6l8oC+L1IB7x7XVTVf9CWRCvB/GIb6+bqvoXyoJ4PYhHfHvdVNW/UBbE60E84tvrpqr+hbIgXg/iEd9eN1X1L5QF8XoQj/j2uqmqf6EsiNeDeMS3101V/QtlQbwexCO+vW6q6l8oC+L1IH764jfz5M1DozJddVNV/0JZEN+H7SLNVzeNynTVTVX9C2VBfB82H+7z7N39YWW66qaq/oWyIL4P2RcPmidU2OHxtSswBmcQv37zXPwEeXztClwcTY+fIIhvp32OnxCIb0eeRNQ8qp8QiH+B1vP4CYF4pyDeKYh3CuKdgninIP4EXvsXy1OI/yfb8TyVjCl+vKLsFmumuoi3US7iIy/WTHURb6NcxEderJnqIt5GuYiPvFgz1eUHHKcg3imIdwrinYJ4pyDeKYh3CuKdgninIN4pY4kf9cL7VZIk1/d1mfsvasJKoNYiTys5lDt2jbNZkqRnqW7NSOLbF9BrWabPytx/UbMWMa1FnlZyKHfsGss6xezt3Rmqu2Mk8aMurtt+untW5v6Ltszl1ffFh1uLPKnkstyxa7wWsct0/Oo+MZL4UZfTFmOZDHRVmfsvJ1SxCFZrkSeWLOWeo8Yv1XOkUI8kftQF9MUgJ32oKnP/5YRSC0GtRZ5YcvhCjV9jWad6jurWxNjjA8vUUI8fv8ab+W1+lurWxDjHB16Y4fQFZmeZ4/fEj1duNkvzF44Z4prjR11AL4PZ9tv7qsz9Fz0SrNYiTyy5nkLGrHHp/SzVrYn1PP7qbuzT13Ofx49Z41VYPJMaOI8HayDeKYh3CuKdgninIN4piHcK4p2CeKcg3imIdwrinYJ4pyDeKYh3CuKdgninIN4piHcK4p3iQ7ysdLnWXZUsS9WmiAvxm3ma56s3D4h/woX48srq9z/Mi26/mYf1zB/+Gq6HXoeRIM93CeXm7POPIbl499nHtFq0vCwXx00EF+K3i/JCdPkCLMNyhM38zcP6OqxKKRcnVAnV5mpBg7xbJ2lYtPzufl28uX29RoyMC/GhZ18FeyKx0C2D//bT3dMatGcJxeZqTpDvRTXUy2e+evhxOo/XdSI+D2twRbwsaL4qjS/DIH5VLm0vE6rNlfjwIvc8WMqMsP30w1eTGel9iA/3GZDVrOWSw7z0XN3NYB2mgSqh2rzf42U0kJTVN9MZ6X2ID0f1ssK4nOML1Zv5jbyI9Ep8mVBtrg//yzm+XgEv/yaDC/HhPL4Y0reLcFRf/LV5/3UY45e7o/oqodxci98uwlH9Kgkv228n9CB1H+IbNO4s0OdWA9mXZ6rNa4D4FxKarK4mNNJ7FQ+IdwrinYJ4pyDeKYh3CuKdgninIN4piHcK4p2CeKcg3imIdwrinYJ4p/wffFlYwaDSAqAAAAAASUVORK5CYII=" alt="plot of chunk unnamed-chunk-3"/> </p>

<h2>What is the average daily activity pattern?</h2>

<p>I used the aggregate() function to calculate the average number of steps for all 288 5-minute intervals across all 61 days. The average was calculated while ignoring missing data.</p>

<pre><code class="r">mean_steps_per_interval &lt;- aggregate(x = xdata$steps, by = list(xdata$interval), 
    FUN = function(x) {
        mean(x, na.rm = T)
    })
</code></pre>

<pre><code class="r">with(mean_steps_per_interval, {
    plot(x = Group.1, y = x, type = &quot;l&quot;, las = 1, xlab = &quot;24h clock time&quot;, ylab = &quot;Average # of steps taken in 5-min interval&quot;, 
        main = &quot;Average daily activity pattern across 61 days&quot;)
})
</code></pre>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAAGwCAMAAABy/YdMAAAAn1BMVEX9/v0AAAAAADkAAGUAOTkAOY8AZo8AZrU5AAA5ADk5AGU5OQA5OTk5OWU5OY85ZmU5ZrU5j485j9plAABlADllAGVlOQBlOY9lZgBlZjllZmVltbVltf2POQCPOTmPOWWPj2WPj9qPtY+P29qP2/21ZgC1tWW124+1/rW1/tq1/v3ajzna24/a/rXa/tra/v39tWX924/9/rX9/tr9/v3AP8C5AAAANXRSTlP/////////////////////////////////////////////////////////////////////AHy10AoAAAAJcEhZcwAACxIAAAsSAdLdfvwAABUOSURBVHic7Z0Le6M2FoYrz2aTaXfTrd3Zq53pTs22jTuNHfP/f9uiKwgECBBIcL73mYltjA4yL7pwEXyTA5J8EzsDIA4QTxSIJwrEEwXiiQLxRIF4okA8USCeKBBPFIgnCsQTBeKJAvFEgXiiQDxRIJ4oEE8UiCcKxBMF4okC8USBeKJAPFEgniiLi7+f2OO0CO+Hh7fy/YdX/r8zQXbMrXnkh2JqN2KG3rlGkDEmf8Htqboqqr9rfhYXf3tiPZ76qK+gPvEZc8lzT63P0DvXCArvTGz8GWOExF/Yv+UalT/9kU9hfMr9tPsX252vxafdWdQMH34Vq0J9Lyimsv/wqWo2VeJ/OxXur2wv5qlEKLYx/pc98vnMIkWCYuqfK6nupw//Y2KTlMnvcgapyMrhz2bO5sL0jxApeNxiMxez6te8rKSKFH8x4mu/665zVkkXmKXFFz/pF17BXXlt934o1pEoAMVvFKv64euBf3p4E5/+9FTMpL+XqZn8+v2gX+VavBRiMi6Ar9hKBCYVC/FmkVr8YyVVPfIfFfF2Dv+Qc0pltYXJzezhLVOzlNmUrzyJ3j7vL8VG/pi7f5fKWTVdYJYWXzRrYnMuisZZ2L9xuXxS2fhzS7enYqZL9XuZWk3Vs+n/Omxei8Crav5fFjG1SNE28KmVVMXS99zTUScvq/paDsWcV2b3M/TC5Cy3J1EZ7c4iqch3OfuVfa9bOyO+8btUzqrpArO0eL4p8//Fn71YrVexrYvqrSyxvHg+ylbPfM+/M1P1bGW9WdQVut7UEWTJMuLNIo3XSiq5AfA5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" alt="plot of chunk unnamed-chunk-5"/> </p>

<p>To find the interval that has on average the highest activity the which() function was used.
It turned out that 8:35 am is the intervall with the highest average activity of 206.17 steps.</p>

<pre><code class="r">with(mean_steps_per_interval, {
    Group.1[which(x == max(x))]
})
</code></pre>

<pre><code>## [1] 835
</code></pre>

<pre><code class="r">
max(mean_steps_per_interval$x)
</code></pre>

<pre><code>## [1] 206.2
</code></pre>

<h2>Imputing missing values</h2>

<h1>Number of missing values</h1>

<p>The number of missing values is 2304</p>

<p>Found with either:</p>

<pre><code class="r">sum(is.na(xdata))
</code></pre>

<pre><code>## [1] 2304
</code></pre>

<p>or</p>

<pre><code class="r">nrow(xdata) - nrow(na.omit(xdata))
</code></pre>

<pre><code>## [1] 2304
</code></pre>

<p>To impute missing data I used the average from the relavant 5-minute interval. First I found the rows_to_impute. Then I copied the steps and filled in the average steps_per_interval into the places where the original steps were NA.</p>

<pre><code class="r">xdata_impute &lt;- xdata
xdata_impute$steps_Imp &lt;- xdata_impute$steps

# find NA_rows
rows_to_impute &lt;- is.na(xdata_impute$steps_Imp)

# create vector that repeats the average interval steps for 61 days
average_int_steps &lt;- rep(mean_steps_per_interval$x, 61)

# use that vector to fill in the average steps for those days with NA_rows
# only
xdata_impute$steps_Imp[rows_to_impute] &lt;- average_int_steps[rows_to_impute]
</code></pre>

<p>Calculate and report the mean and median total number of steps taken per day. Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?</p>

<pre><code class="r">sum_steps_daily_Imp &lt;- aggregate(x = xdata_impute$steps_Imp, by = list(xdata_impute$date), 
    FUN = sum)
</code></pre>

<p>The mean daily steps for the imputed data is 1.0766 &times; 10<sup>4</sup>. The Median is also 1.0766 &times; 10<sup>4</sup> Therefore the mean and median did not change from the raw data to the imputed data. The reason is, that the missing values are imputed with averaged values and therefor sum up to the before average values again.</p>

<pre><code class="r">hist(sum_steps_daily_Imp$x, breaks = 20, col = &quot;grey&quot;, ylim = c(0, 20), main = &quot;Histogram of steps per day (imputed data)&quot;, 
    las = 1, xlab = &quot;Steps per day&quot;)

abline(abline(v = mean(sum_steps_daily_Imp$x, na.rm = T), col = &quot;red&quot;))
text(x = mean(sum_steps_daily_Imp$x, na.rm = T), y = 20, labels = &quot;Mean (imputed data)&quot;)
</code></pre>

<p><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAfgAAAGwCAMAAABy/YdMAAAAulBMVEX9/v0AAAAAADkAAGUAOTkAOWUAOY8AZo8AZrU5AAA5ADk5AGU5OWU5OY85Zo85ZrU5j485j9plAABlADllAGVlOQBlOTllOY9lZjllZmVlZrVltbVltf1mAACPOQCPOTmPOWWPZgCPZo+PjzmPj2WPtY+P27WP2/2QAAC1ZgC1Zjm1tWW124+1/rW1/tq1/v22AAC+vr7ajznaj2Xa/rXa/tra/v3bAAD9tWX924/9/rX9/tr9/v3/AAA8AhG1AAAAPnRSTlP///////////////////////////////////////////////////////////////////////////////8A/wTdY8kAAAAJcEhZcwAACxIAAAsSAdLdfvwAABCISURBVHic7Z0Ne6PGFUaD3Lj2uttE8qZJWqrdNNmo5KNq1NQVEvv//1bn3hlACGzgCiwu9z3PsysJhtHwHs3wYYE+y4BJPrt2A8B1gHijQLxRIN4oEG8UiDcKxBsF4o0C8UaBeKNAvFEg3igQbxSINwrEGwXijQLxRoF4o0C8USDeKBBvFIg3CsQbBeKNAvFGuZb4w+pmm2XH9c3WP8tJ4gsqTe+jxaYy5aLqmMPq9qlxxm6xqTa9mVoLKhVWaz8pm94v+7SyP9cXX5mcRPEFldaWvqw65jnxh9WdqEkviK+UTdo/UxdxffH8zPXV6GZ7XEdR5PLcuQf6wLvXN7+6aI7rxTeuL+/dZNej99Ef3fStKxSHynx5XtrnWK8u5jf7mSbns3nRcmJZjN/Mz4yiv5Ea/878Md1Hy/CeMa/EaWuKyrikk/rfagvKChtr57JhJYv3GYtpiD+sIpIWckrohXvkKP5wT+Jp7u++0NM+ygnyQvlSfFN14YNBJcJsjr+YWC3GM2sLkOwk/0y4Ry++bE2xwJn4Wguyhtp92aJtz25iBuJ64vO0KL30PqwljXbpPWe62KT3Lr4d5xjd5YtR1LRAFFMRmlaUL8bKs+rcCzLhalnS+8bF7IzjP5kYioU3K94/f+f0/i7fOLGX89YUleXin6otqFRYq71oPr+obQUHZhri+RWtKK37noN3vYufHPxQv8kXoqjvOJt8alH+JLlKdUwYqV25ZTE7y/cy3MSTYvkOYvH++Tsf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" alt="plot of chunk unnamed-chunk-11"/> </p>

<p>By imputing missing values with average value the bin around the mean and median increased compared to the raw data.</p>

<h2>Are there differences in activity patterns between weekdays and weekends?</h2>

<p>First I add a weekday column with the weekdays() function and the as.Date() transformation function. Then a column called $week_part is created where &ldquo;Samstag&rdquo; and &ldquo;Sonntag&rdquo; refer to &ldquo;weekend&rdquo; and the other days to &ldquo;weekdays&rdquo;.</p>

<pre><code class="r">xdata_impute$weekdays &lt;- weekdays(as.Date(xdata_impute$date))

xdata_impute$week_part &lt;- NA
xdata_impute$week_part[xdata_impute$weekdays %in% c(&quot;Samstag&quot;, &quot;Sonntag&quot;)] &lt;- &quot;weekend&quot;
xdata_impute$week_part[!xdata_impute$weekdays %in% c(&quot;Samstag&quot;, &quot;Sonntag&quot;)] &lt;- &quot;weekday&quot;

xdata_impute$week_part &lt;- as.factor(xdata_impute$week_part)
</code></pre>

<p>I created two separate data frames to calculate the average number of steps for the two different week_part categories.</p>

<pre><code class="r">library(lattice)

weekday_df &lt;- xdata_impute[xdata_impute$week_part == &quot;weekday&quot;, ]
weekend_df &lt;- xdata_impute[xdata_impute$week_part == &quot;weekend&quot;, ]

MSpI_weekday &lt;- aggregate(x = weekday_df$steps_Imp, by = list(weekday_df$interval), 
    FUN = function(x) {
        mean(x, na.rm = T)
    })

MSpI_weekend &lt;- aggregate(x = weekend_df$steps_Imp, by = list(weekend_df$interval), 
    FUN = function(x) {
        mean(x, na.rm = T)
    })
</code></pre>

<p>I plotted the data with the Lattice plotting system after rbind() combining the two data.frames.</p>

<pre><code class="r">MSpI_weekday$weekpart &lt;- rep(&quot;weekday&quot;, nrow(MSpI_weekday))
MSpI_weekend$weekpart &lt;- rep(&quot;weekend&quot;, nrow(MSpI_weekend))
lat_data &lt;- rbind(MSpI_weekday, MSpI_weekend)
lat_data$weekpart &lt;- as.factor(lat_data$weekpart)
</code></pre>

<pre><code class="r">
xyplot(data = lat_data, x ~ Group.1 | weekpart, layout = c(1, 2), type = &quot;l&quot;, 
    xlab = &quot;24h clock time&quot;, ylab = &quot;Average steps per 5-minutes interval&quot;)
</code></pre>

<p><img src="data:image/png;base64,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" alt="plot of chunk unnamed-chunk-15"/> </p>

<p>There seems to be a higher average activity on weekdays compared to the activity on weekends. Especially past 10 am in the morning. Untill then the activity seems rather similar.</p>

</body>

</html>

