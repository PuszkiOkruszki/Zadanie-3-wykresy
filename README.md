chart = {
  const svg = d3.create("svg")
      .attr("viewBox", [0, 0, width, height]);

  svg.append("g")
      .call(xAxis);

  svg.append("g")
      .call(yAxis);

  svg.append("path")
      .datum(data)
      .attr("fill", "none")
      .attr("stroke", "steelblue")
      .attr("stroke-width", 1.5)
      .attr("stroke-linejoin", "round")
      .attr("stroke-linecap", "round")
      .attr("d", line);

  return svg.node();
}
data = Array(1280) [
  0: Object {date: 2007-04-23, value: 93.24}
  1: Object {date: 2007-04-24, value: 95.35}
  2: Object {date: 2007-04-25, value: 98.84}
  3: Object {date: 2007-04-26, value: 99.92}
  4: Object {date: 2007-04-29, value: 99.8}
  5: Object {date: 2007-05-01, value: 99.47}
  6: Object {date: 2007-05-02, value: 100.39}
  7: Object {date: 2007-05-03, value: 100.4}
  8: Object {date: 2007-05-04, value: 100.81}
  9: Object {date: 2007-05-07, value: 103.92}
  10: Object {date: 2007-05-08, value: 105.06}
  11: Object {date: 2007-05-09, value: 106.88}
  12: Object {date: 2007-05-09, value: 107.34}
  13: Object {date: 2007-05-10, value: 108.74}
  14: Object {date: 2007-05-13, value: 109.36}
  15: Object {date: 2007-05-14, value: 107.52}
  16: Object {date: 2007-05-15, value: 107.34}
  17: Object {date: 2007-05-16, value: 109.44}
  18: Object {date: 2007-05-17, value: 110.02}
  19: Object {date: 2007-05-20, value: 111.98}
  20: Object {date: 2007-05-21, value: 113.54}
  21: Object {date: 2007-05-22, value: 112.89}
  22: Object {date: 2007-05-23, value: 110.69}
  23: Object {date: 2007-05-24, value: 113.62}
  24: Object {date: 2007-05-28, value: 114.35}
  25: Object {date: 2007-05-29, value: 118.77}
  26: Object {date: 2007-05-30, value: 121.19}
  27: Object {date: 2007-06-01, value: 118.4}
  28: Object {date: 2007-06-04, value: 121.33}
  29: Object {date: 2007-06-05, value: 122.67}
  30: Object {date: 2007-06-06, value: 123.64}
  31: Object {date: 2007-06-07, value: 124.07}
  32: Object {date: 2007-06-08, value: 124.49}
  33: Object {date: 2007-06-10, value: 120.19}
  34: Object {date: 2007-06-11, value: 120.38}
  35: Object {date: 2007-06-12, value: 117.5}
  36: Object {date: 2007-06-13, value: 118.75}
  37: Object {date: 2007-06-14, value: 120.5}
  38: Object {date: 2007-06-17, value: 125.09}
  39: Object {date: 2007-06-18, value: 123.66}
  40: Object {date: 2007-06-19, value: 121.55}
  41: Object {date: 2007-06-20, value: 123.9}
  42: Object {date: 2007-06-21, value: 123}
  43: Object {date: 2007-06-24, value: 122.34}
  44: Object {date: 2007-06-25, value: 119.65}
  45: Object {date: 2007-06-26, value: 121.89}
  46: Object {date: 2007-06-27, value: 120.56}
  47: Object {date: 2007-06-28, value: 122.04}
  48: Object {date: 2007-07-02, value: 121.26}
  49: Object {date: 2007-07-03, value: 127.17}
  50: Object {date: 2007-07-05, value: 132.75}
  51: Object {date: 2007-07-06, value: 132.3}
  52: Object {date: 2007-07-09, value: 130.33}
  53: Object {date: 2007-07-09, value: 132.35}
  54: Object {date: 2007-07-10, value: 132.39}
  55: Object {date: 2007-07-11, value: 134.07}
  56: Object {date: 2007-07-12, value: 137.73}
  57: Object {date: 2007-07-15, value: 138.1}
  58: Object {date: 2007-07-16, value: 138.91}
  59: Object {date: 2007-07-17, value: 138.12}
  60: Object {date: 2007-07-18, value: 140}
  61: Object {date: 2007-07-19, value: 143.75}
  62: Object {date: 2007-07-22, value: 143.7}
  63: Object {date: 2007-07-23, value: 134.89}
  64: Object {date: 2007-07-24, value: 137.26}
  65: Object {date: 2007-07-25, value: 146}
  66: Object {date: 2007-07-26, value: 143.85}
  67: Object {date: 2007-07-29, value: 141.43}
  68: Object {date: 2007-07-30, value: 131.76}
  69: Object {date: 2007-08-01, value: 135}
  70: Object {date: 2007-08-02, value: 136.49}
  ]
  data = Object.assign((d3.csvParse(await FileAttachment("aapl.csv").text(), d3.autoType)).map(({date, close}) => ({date, value: close})), {y: "$ Close"})
  line = ƒ(a)
  line = d3.line()
    .defined(d => !isNaN(d.value))
    .x(d => x(d.date))
    .y(d => y(d.value))
    x = ƒ(n)
    x = d3.scaleUtc()
    .domain(d3.extent(data, d => d.date))
    .range([margin.left, width - margin.right])
    y = ƒ(n)
    y = d3.scaleLinear()
    .domain([0, d3.max(data, d => d.value)]).nice()
    .range([height - margin.bottom, margin.top])
    xAxis = ƒ(g)
    xAxis = g => g
    .attr("transform", `translate(0,${height - margin.bottom})`)
    .call(d3.axisBottom(x).ticks(width / 80).tickSizeOuter(0))
    yAxis = ƒ(g)
    yAxis = g => g
    .attr("transform", `translate(${margin.left},0)`)
    .call(d3.axisLeft(y))
    .call(g => g.select(".domain").remove())
    .call(g => g.select(".tick:last-of-type text").clone()
        .attr("x", 3)
        .attr("text-anchor", "start")
        .attr("font-weight", "bold")
        .text(data.y))
        margin = Object {
  top: 20
  right: 30
  bottom: 30
  left: 40
}
margin = ({top: 20, right: 30, bottom: 30, left: 40})
height = 500
height = 500
d3 = Object {
  format: ƒ(t)
  formatPrefix: ƒ(t, n)
  timeFormat: ƒ(t)
  timeParse: ƒ(t)
  utcFormat: ƒ(t)
  utcParse: ƒ(t)
  Adder: class
  Delaunay: class
  FormatSpecifier: ƒ(t)
  InternMap: class
  InternSet: class
  Voronoi: class
  active: ƒ(t, n)
  arc: ƒ()
  area: ƒ(t, n, e)
  areaRadial: ƒ()
  ascending: ƒ(t, n)
  autoType: ƒ(t)
  axisBottom: ƒ(t)
  axisLeft: ƒ(t)
  axisRight: ƒ(t)
  axisTop: ƒ(t)
  bin: ƒ()
  bisect: ƒ(t, n, e, i)
  bisectCenter: ƒ(t, n, r, o)
  bisectLeft: ƒ(t, n, e, i)
  bisectRight: ƒ(t, n, e, i)
  bisector: ƒ(t)
  blob: ƒ(t, n)
  brush: ƒ()
  brushSelection: ƒ(t)
  brushX: ƒ()
  brushY: ƒ()
  buffer: ƒ(t, n)
  chord: ƒ()
  chordDirected: ƒ()
  chordTranspose: ƒ()
  cluster: ƒ()
  color: ƒ(t)
  contourDensity: ƒ()
  contours: ƒ()
  count: ƒ(t, n)
  create: ƒ(t)
  creator: ƒ(t)
  cross: ƒ(…)
  csv: ƒ(n, e, r)
  csvFormat: ƒ(n, e)
  csvFormatBody: ƒ(t, n)
  csvFormatRow: ƒ(n)
  csvFormatRows: ƒ(t)
  csvFormatValue: ƒ(t)
  csvParse: ƒ(t, n)
  csvParseRows: ƒ(t, n)
  cubehelix: ƒ(t, n, e, r)
  cumsum: ƒ(t, n)
  curveBasis: ƒ(t)
  curveBasisClosed: ƒ(t)
  curveBasisOpen: ƒ(t)
  curveBumpX: ƒ(t)
  curveBumpY: ƒ(t)
  curveBundle: ƒ(t)
  curveCardinal: ƒ(t)
  curveCardinalClosed: ƒ(t)
  curveCardinalOpen: ƒ(t)
  curveCatmullRom: ƒ(t)
  curveCatmullRomClosed: ƒ(t)
  curveCatmullRomOpen: ƒ(t)
  curveLinear: ƒ(t)
  curveLinearClosed: ƒ(t)
  curveMonotoneX: ƒ(t)
  curveMonotoneY: ƒ(t)
  curveNatural: ƒ(t)
  curveStep: ƒ(t)
  curveStepAfter: ƒ(t)
  curveStepBefore: ƒ(t)
  descending: ƒ(t, n)
  deviation: ƒ(t, n)
  difference: ƒ(…)
  disjoint: ƒ(t, n)
  dispatch: ƒ()
  drag: ƒ()
  dragDisable: ƒ(t)
  dragEnable: ƒ(t, n)
  dsv: ƒ(t, n, e, r)
  dsvFormat: ƒ(t)
  easeBack: ƒ(t)
  easeBackIn: ƒ(t)
  easeBackInOut: ƒ(t)
  easeBackOut: ƒ(t)
  easeBounce: ƒ(t)
  easeBounceIn: ƒ(t)
  easeBounceInOut: ƒ(t)
  easeBounceOut: ƒ(t)
  easeCircle: ƒ(t)
  easeCircleIn: ƒ(t)
  easeCircleInOut: ƒ(t)
  easeCircleOut: ƒ(t)
  easeCubic: ƒ(…)
  easeCubicIn: ƒ(t)
  easeCubicInOut: ƒ(…)
  easeCubicOut: ƒ(t)
  easeElastic: ƒ(t)
  easeElasticIn: ƒ(t)
  easeElasticInOut: ƒ(t)
  easeElasticOut: ƒ(t)
  easeExp: ƒ(t)
  easeExpIn: ƒ(t)
  easeExpInOut: ƒ(t)
  easeExpOut: ƒ(t)
  easeLinear: ƒ(t)
  easePoly: ƒ(t)
  easePolyIn: ƒ(t)
  easePolyInOut: ƒ(t)
  easePolyOut: ƒ(t)
  easeQuad: ƒ(t)
  easeQuadIn: ƒ(t)
  easeQuadInOut: ƒ(t)
  easeQuadOut: ƒ(t)
  easeSin: ƒ(t)
  easeSinIn: ƒ(t)
  easeSinInOut: ƒ(t)
  easeSinOut: ƒ(t)
  every: ƒ(t, n)
  extent: ƒ(t, n)
  fcumsum: ƒ(t, n)
  filter: ƒ(t, n)
  forceCenter: ƒ(t, n)
  forceCollide: ƒ(t)
  forceLink: ƒ(t)
  forceManyBody: ƒ()
  forceRadial: ƒ(t, n, e)
  forceSimulation: ƒ(t)
  forceX: ƒ(t)
  forceY: ƒ(t)
  formatDefaultLocale: ƒ(n)
  formatLocale: ƒ(t)
  formatSpecifier: ƒ(t)
  fsum: ƒ(t, n)
  geoAlbers: ƒ()
  geoAlbersUsa: ƒ()
  geoArea: ƒ(t)
  geoAzimuthalEqualArea: ƒ()
  geoAzimuthalEqualAreaRaw: ƒ(n, e)
  geoAzimuthalEquidistant: ƒ()
  geoAzimuthalEquidistantRaw: ƒ(n, e)
  geoBounds: ƒ(t)
  geoCentroid: ƒ(t)
  geoCircle: ƒ()
  geoClipAntimeridian: ƒ(i)
  geoClipCircle: ƒ(t)
  geoClipExtent: ƒ()
  geoClipRectangle: ƒ(t, n, e, r)
  geoConicConformal: ƒ()
  geoConicConformalRaw: ƒ(t, n)
  geoConicEqualArea: ƒ()
  geoConicEqualAreaRaw: ƒ(t, n)
  geoConicEquidistant: ƒ()
  geoConicEquidistantRaw: ƒ(t, n)
  geoContains: ƒ(t, n)
  geoDistance: ƒ(t, n)
  geoEqualEarth: ƒ()
  geoEqualEarthRaw: ƒ(t, n)
  geoEquirectangular: ƒ()
  geoEquirectangularRaw: ƒ(t, n)
  geoGnomonic: ƒ()
  geoGnomonicRaw: ƒ(t, n)
  geoGraticule: ƒ()
  geoGraticule10: ƒ()
  geoIdentity: ƒ()
  geoInterpolate: ƒ(t, n)
  geoLength: ƒ(t)
  geoMercator: ƒ()
  geoMercatorRaw: ƒ(t, n)
  geoNaturalEarth1: ƒ()
  geoNaturalEarth1Raw: ƒ(t, n)
  geoOrthographic: ƒ()
  geoOrthographicRaw: ƒ(t, n)
  geoPath: ƒ(t, n)
  geoProjection: ƒ(t)
  geoProjectionMutator: ƒ(t)
  geoRotation: ƒ(t)
  geoStereographic: ƒ()
  geoStereographicRaw: ƒ(t, n)
  geoStream: ƒ(t, n)
  geoTransform: ƒ(t)
  geoTransverseMercator: ƒ()
  geoTransverseMercatorRaw: ƒ(t, n)
  gray: ƒ(t, n)
  greatest: ƒ(…)
  greatestIndex: ƒ(…)
  group: ƒ(…)
  groupSort: ƒ(t, e, r)
  groups: ƒ(…)
  hcl: ƒ(t, n, e, r)
  hierarchy: ƒ(t, n)
  histogram: ƒ()
  hsl: ƒ(t, n, e, r)
  html: ƒ(n, e)
  image: ƒ(t, n)
  index: ƒ(…)
  indexes: ƒ(…)
  interpolate: ƒ(t, n)
  interpolateArray: ƒ(t, n)
  interpolateBasis: ƒ(t)
  interpolateBasisClosed: ƒ(t)
  interpolateBlues: ƒ(t)
  interpolateBrBG: ƒ(t)
  interpolateBuGn: ƒ(t)
  interpolateBuPu: ƒ(t)
  interpolateCividis: ƒ(t)
  interpolateCool: ƒ(t)
  interpolateCubehelix: ƒ(n, r)
  interpolateCubehelixDefault: ƒ(t)
  interpolateCubehelixLong: ƒ(n, r)
  interpolateDate: ƒ(t, n)
  interpolateDiscrete: ƒ(t)
  interpolateGnBu: ƒ(t)
  interpolateGreens: ƒ(t)
  interpolateGreys: ƒ(t)
  interpolateHcl: ƒ(n, e)
  interpolateHclLong: ƒ(n, e)
  interpolateHsl: ƒ(n, e)
  interpolateHslLong: ƒ(n, e)
  interpolateHue: ƒ(t, n)
  interpolateInferno: ƒ(e)
  interpolateLab: ƒ(t, n)
  interpolateMagma: ƒ(e)
  interpolateNumber: ƒ(t, n)
  interpolateNumberArray: ƒ(t, n)
  interpolateObject: ƒ(t, n)
  interpolateOrRd: ƒ(t)
  interpolateOranges: ƒ(t)
  interpolatePRGn: ƒ(t)
  interpolatePiYG: ƒ(t)
  interpolatePlasma: ƒ(e)
  interpolatePuBu: ƒ(t)
  interpolatePuBuGn: ƒ(t)
  interpolatePuOr: ƒ(t)
  interpolatePuRd: ƒ(t)
  interpolatePurples: ƒ(t)
  interpolateRainbow: ƒ(t)
  interpolateRdBu: ƒ(t)
  interpolateRdGy: ƒ(t)
  interpolateRdPu: ƒ(t)
  interpolateRdYlBu: ƒ(t)
  interpolateRdYlGn: ƒ(t)
  interpolateReds: ƒ(t)
  interpolateRgb: ƒ(t, n)
  interpolateRgbBasis: ƒ(n)
  interpolateRgbBasisClosed: ƒ(n)
  interpolateRound: ƒ(t, n)
  interpolateSinebow: ƒ(t)
  interpolateSpectral: ƒ(t)
  interpolateString: ƒ(t, n)
  interpolateTransformCss: ƒ(o, a)
  interpolateTransformSvg: ƒ(o, a)
  interpolateTurbo: ƒ(t)
  interpolateViridis: ƒ(e)
  interpolateWarm: ƒ(t)
  interpolateYlGn: ƒ(t)
  interpolateYlGnBu: ƒ(t)
  interpolateYlOrBr: ƒ(t)
  interpolateYlOrRd: ƒ(t)
  interpolateZoom: ƒ(t, i)
  interrupt: ƒ(t, n)
  intersection: ƒ(…)
  interval: ƒ(t, n, e)
  isoFormat: ƒ(t)
  isoParse: ƒ(t)
  json: ƒ(t, n)
  lab: ƒ(t, n, e, r)
  lch: ƒ(t, n, e, r)
  least: ƒ(…)
  leastIndex: ƒ(…)
  line: ƒ(t, n)
  lineRadial: ƒ()
  linkHorizontal: ƒ()
  linkRadial: ƒ()
  linkVertical: ƒ()
  local: ƒ()
  map: ƒ(t, n)
  matcher: ƒ(t)
  max: ƒ(t, n)
  maxIndex: ƒ(t, n)
  mean: ƒ(t, n)
  median: ƒ(t, n)
  merge: ƒ(t)
  min: ƒ(t, n)
  minIndex: ƒ(…)
  namespace: ƒ(t)
  namespaces: Object {svg: "http://www.w3.org/2000/svg", xhtml: "http://www.w3.org/1999/xhtml", xlink: "http://www.w3.org/1999/xlink", xml: "http://www.w3.org/XML/1998/namespace", xmlns: "http://www.w3.org/2000/xmlns/"}
  nice: ƒ(t, n, e)
  now: ƒ()
  pack: ƒ()
  packEnclose: ƒ(t)
  packSiblings: ƒ(t)
  pairs: ƒ(…)
  partition: ƒ()
  path: ƒ()
  permute: ƒ(t, n)
  pie: ƒ()
  piecewise: ƒ(t, n)
  pointRadial: ƒ(t, n)
  pointer: ƒ(t, n)
  pointers: ƒ(t, n)
  polygonArea: ƒ(t)
  polygonCentroid: ƒ(t)
  polygonContains: ƒ(t, n)
  polygonHull: ƒ(t)
  polygonLength: ƒ(t)
  precisionFixed: ƒ(t)
  precisionPrefix: ƒ(t, n)
  precisionRound: ƒ(t, n)
  quadtree: ƒ(t, n, e)
  quantile: ƒ(t, n, e)
  quantileSorted: ƒ(…)
  quantize: ƒ(t, n)
  quickselect: ƒ(…)
  radialArea: ƒ()
  radialLine: ƒ()
  randomBates: ƒ(t)
  randomBernoulli: ƒ(t)
  randomBeta: ƒ(t, n)
  randomBinomial: ƒ(t, n)
  randomCauchy: ƒ(t, e)
  randomExponential: ƒ(t)
  randomGamma: ƒ(t, r)
  randomGeometric: ƒ(t)
  randomInt: ƒ(t, e)
  randomIrwinHall: ƒ(t)
  randomLcg: ƒ(…)
  randomLogNormal: ƒ()
  randomLogistic: ƒ(t, e)
  randomNormal: ƒ(t, e)
  randomPareto: ƒ(t)
  randomPoisson: ƒ(t)
  randomUniform: ƒ(t, e)
  randomWeibull: ƒ(t, e, r)
  range: ƒ(t, n, e)
  reduce: ƒ(t, n, e)
  reverse: ƒ(t)
  rgb: ƒ(t, n, e, r)
  ribbon: ƒ()
  ribbonArrow: ƒ()
  rollup: ƒ(…)
  rollups: ƒ(…)
  scaleBand: ƒ()
  scaleDiverging: ƒ()
  scaleDivergingLog: ƒ()
  scaleDivergingPow: ƒ()
  scaleDivergingSqrt: ƒ()
  scaleDivergingSymlog: ƒ()
  scaleIdentity: ƒ(n)
  scaleImplicit: Symbol(implicit)
  scaleLinear: ƒ()
  scaleLog: ƒ()
  scaleOrdinal: ƒ()
  scalePoint: ƒ()
  scalePow: ƒ()
  scaleQuantile: ƒ()
  scaleQuantize: ƒ()
  scaleRadial: ƒ()
  scaleSequential: ƒ()
  scaleSequentialLog: ƒ()
  scaleSequentialPow: ƒ()
  scaleSequentialQuantile: ƒ()
  scaleSequentialSqrt: ƒ()
  scaleSequentialSymlog: ƒ()
  scaleSqrt: ƒ()
  scaleSymlog: ƒ()
  scaleThreshold: ƒ()
  scaleTime: ƒ()
  scaleUtc: ƒ()
  scan: ƒ(t, n)
  schemeAccent: Array(8) ["#7fc97f", "#beaed4", "#fdc086", "#ffff99", "#386cb0", "#f0027f", "#bf5b17", "#666666"]
  schemeBlues: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeBrBG: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeBuGn: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeBuPu: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeCategory10: Array(10) ["#1f77b4", "#ff7f0e", "#2ca02c", "#d62728", "#9467bd", "#8c564b", "#e377c2", "#7f7f7f", "#bcbd22", "#17becf"]
  schemeDark2: Array(8) ["#1b9e77", "#d95f02", "#7570b3", "#e7298a", "#66a61e", "#e6ab02", "#a6761d", "#666666"]
  schemeGnBu: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeGreens: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeGreys: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeOrRd: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeOranges: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePRGn: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePaired: Array(12) ["#a6cee3", "#1f78b4", "#b2df8a", "#33a02c", "#fb9a99", "#e31a1c", "#fdbf6f", "#ff7f00", "#cab2d6", "#6a3d9a", "#ffff99", "#b15928"]
  schemePastel1: Array(9) ["#fbb4ae", "#b3cde3", "#ccebc5", "#decbe4", "#fed9a6", "#ffffcc", "#e5d8bd", "#fddaec", "#f2f2f2"]
  schemePastel2: Array(8) ["#b3e2cd", "#fdcdac", "#cbd5e8", "#f4cae4", "#e6f5c9", "#fff2ae", "#f1e2cc", "#cccccc"]
  schemePiYG: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePuBu: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePuBuGn: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePuOr: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePuRd: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePurples: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeRdBu: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdGy: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdPu: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeRdYlBu: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdYlGn: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeReds: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeSet1: Array(9) ["#e41a1c", "#377eb8", "#4daf4a", "#984ea3", "#ff7f00", "#ffff33", "#a65628", "#f781bf", "#999999"]
  schemeSet2: Array(8) ["#66c2a5", "#fc8d62", "#8da0cb", "#e78ac3", "#a6d854", "#ffd92f", "#e5c494", "#b3b3b3"]
  schemeSet3: Array(12) ["#8dd3c7", "#ffffb3", "#bebada", "#fb8072", "#80b1d3", "#fdb462", "#b3de69", "#fccde5", "#d9d9d9", "#bc80bd", "#ccebc5", "#ffed6f"]
  schemeSpectral: Array(12) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeTableau10: Array(10) ["#4e79a7", "#f28e2c", "#e15759", "#76b7b2", "#59a14f", "#edc949", "#af7aa1", "#ff9da7", "#9c755f", "#bab0ab"]
  schemeYlGn: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlGnBu: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlOrBr: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlOrRd: Array(10) [empty × 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  select: ƒ(t)
  selectAll: ƒ(t)
  selection: ƒ()
  selector: ƒ(t)
  selectorAll: ƒ(t)
  shuffle: ƒ(…)
  shuffler: ƒ(t)
  some: ƒ(t, n)
  sort: ƒ(…)
  stack: ƒ()
  stackOffsetDiverging: ƒ(t, n)
  stackOffsetExpand: ƒ(t, n)
  stackOffsetNone: ƒ(t, n)
  stackOffsetSilhouette: ƒ(t, n)
  stackOffsetWiggle: ƒ(t, n)
  stackOrderAppearance: ƒ(…)
  stackOrderAscending: ƒ(t)
  stackOrderDescending: ƒ(t)
  stackOrderInsideOut: ƒ(t)
  stackOrderNone: ƒ(t)
  stackOrderReverse: ƒ(t)
  stratify: ƒ()
  style: ƒ(t, n)
  subset: ƒ(t, n)
  sum: ƒ(t, n)
  superset: ƒ(t, n)
  svg: ƒ(n, e)
  symbol: ƒ(t, n)
  symbolCircle: Object {draw: ƒ(t, n)}
  symbolCross: Object {draw: ƒ(t, n)}
  symbolDiamond: Object {draw: ƒ(t, n)}
  symbolSquare: Object {draw: ƒ(t, n)}
  symbolStar: Object {draw: ƒ(t, n)}
  symbolTriangle: Object {draw: ƒ(t, n)}
  symbolWye: Object {draw: ƒ(t, n)}
  symbols: Array(7) [Object, Object, Object, Object, Object, Object, Object]
  text: ƒ(t, n)
  thresholdFreedmanDiaconis: ƒ(t, n, e)
  thresholdScott: ƒ(t, n, e)
  thresholdSturges: ƒ(t)
  tickFormat: ƒ(n, e, r, i)
  tickIncrement: ƒ(t, n, e)
  tickStep: ƒ(t, n, e)
  ticks: ƒ(t, n, e)
  timeDay: ƒ(n)
  timeDays: ƒ(e, r, o)
  timeFormatDefaultLocale: ƒ(n)
  timeFormatLocale: ƒ(t)
  timeFriday: ƒ(n)
  timeFridays: ƒ(e, r, o)
  timeHour: ƒ(n)
  timeHours: ƒ(e, r, o)
  timeInterval: ƒ(t, n, e, r)
  timeMillisecond: ƒ(n)
  timeMilliseconds: ƒ(e, r, o)
  timeMinute: ƒ(n)
  timeMinutes: ƒ(e, r, o)
  timeMonday: ƒ(n)
  timeMondays: ƒ(e, r, o)
  timeMonth: ƒ(n)
  timeMonths: ƒ(e, r, o)
  timeSaturday: ƒ(n)
  timeSaturdays: ƒ(e, r, o)
  timeSecond: ƒ(n)
  timeSeconds: ƒ(e, r, o)
  timeSunday: ƒ(n)
  timeSundays: ƒ(e, r, o)
  timeThursday: ƒ(n)
  timeThursdays: ƒ(e, r, o)
  timeTickInterval: ƒ(n, r, i)
  timeTicks: ƒ(t, n, e)
  timeTuesday: ƒ(n)
  timeTuesdays: ƒ(e, r, o)
  timeWednesday: ƒ(n)
  timeWednesdays: ƒ(e, r, o)
  timeWeek: ƒ(n)
  timeWeeks: ƒ(e, r, o)
  timeYear: ƒ(n)
  timeYears: ƒ(e, r, o)
  timeout: ƒ(t, n, e)
  timer: ƒ(t, n, e)
  timerFlush: ƒ()
  transition: ƒ(t)
  transpose: ƒ(t)
  tree: ƒ()
  treemap: ƒ()
  treemapBinary: ƒ(t, n, e, r, i)
  treemapDice: ƒ(t, n, e, r, i)
  treemapResquarify: ƒ(t, e, r, i, o)
  treemapSlice: ƒ(t, n, e, r, i)
  treemapSliceDice: ƒ(t, n, e, r, i)
  treemapSquarify: ƒ(t, e, r, i, o)
  tsv: ƒ(n, e, r)
  tsvFormat: ƒ(n, e)
  tsvFormatBody: ƒ(t, n)
  tsvFormatRow: ƒ(n)
  tsvFormatRows: ƒ(t)
  tsvFormatValue: ƒ(t)
  tsvParse: ƒ(t, n)
  tsvParseRows: ƒ(t, n)
  union: ƒ(…)
  utcDay: ƒ(n)
  utcDays: ƒ(e, r, o)
  utcFriday: ƒ(n)
  utcFridays: ƒ(e, r, o)
  utcHour: ƒ(n)
  utcHours: ƒ(e, r, o)
  utcMillisecond: ƒ(n)
  utcMilliseconds: ƒ(e, r, o)
  utcMinute: ƒ(n)
  utcMinutes: ƒ(e, r, o)
  utcMonday: ƒ(n)
  utcMondays: ƒ(e, r, o)
  utcMonth: ƒ(n)
  utcMonths: ƒ(e, r, o)
  utcSaturday: ƒ(n)
  utcSaturdays: ƒ(e, r, o)
  utcSecond: ƒ(n)
  utcSeconds: ƒ(e, r, o)
  utcSunday: ƒ(n)
  utcSundays: ƒ(e, r, o)
  utcThursday: ƒ(n)
  utcThursdays: ƒ(e, r, o)
  utcTickInterval: ƒ(n, r, i)
  utcTicks: ƒ(t, n, e)
  utcTuesday: ƒ(n)
  utcTuesdays: ƒ(e, r, o)
  utcWednesday: ƒ(n)
  utcWednesdays: ƒ(e, r, o)
  utcWeek: ƒ(n)
  utcWeeks: ƒ(e, r, o)
  utcYear: ƒ(n)
  utcYears: ƒ(e, r, o)
  variance: ƒ(t, n)
  version: "6.7.0"
  window: ƒ(t)
  xml: ƒ(n, e)
  zip: ƒ()
  zoom: ƒ()
  zoomIdentity: tx {k: 1, x: 0, y: 0}
  zoomTransform: ƒ(t)
}
d3 = require("d3@6")
