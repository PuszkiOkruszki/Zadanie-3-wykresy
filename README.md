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
  line = ??(a)
  line = d3.line()
    .defined(d => !isNaN(d.value))
    .x(d => x(d.date))
    .y(d => y(d.value))
    x = ??(n)
    x = d3.scaleUtc()
    .domain(d3.extent(data, d => d.date))
    .range([margin.left, width - margin.right])
    y = ??(n)
    y = d3.scaleLinear()
    .domain([0, d3.max(data, d => d.value)]).nice()
    .range([height - margin.bottom, margin.top])
    xAxis = ??(g)
    xAxis = g => g
    .attr("transform", `translate(0,${height - margin.bottom})`)
    .call(d3.axisBottom(x).ticks(width / 80).tickSizeOuter(0))
    yAxis = ??(g)
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
  format: ??(t)
  formatPrefix: ??(t, n)
  timeFormat: ??(t)
  timeParse: ??(t)
  utcFormat: ??(t)
  utcParse: ??(t)
  Adder: class
  Delaunay: class
  FormatSpecifier: ??(t)
  InternMap: class
  InternSet: class
  Voronoi: class
  active: ??(t, n)
  arc: ??()
  area: ??(t, n, e)
  areaRadial: ??()
  ascending: ??(t, n)
  autoType: ??(t)
  axisBottom: ??(t)
  axisLeft: ??(t)
  axisRight: ??(t)
  axisTop: ??(t)
  bin: ??()
  bisect: ??(t, n, e, i)
  bisectCenter: ??(t, n, r, o)
  bisectLeft: ??(t, n, e, i)
  bisectRight: ??(t, n, e, i)
  bisector: ??(t)
  blob: ??(t, n)
  brush: ??()
  brushSelection: ??(t)
  brushX: ??()
  brushY: ??()
  buffer: ??(t, n)
  chord: ??()
  chordDirected: ??()
  chordTranspose: ??()
  cluster: ??()
  color: ??(t)
  contourDensity: ??()
  contours: ??()
  count: ??(t, n)
  create: ??(t)
  creator: ??(t)
  cross: ??(???)
  csv: ??(n, e, r)
  csvFormat: ??(n, e)
  csvFormatBody: ??(t, n)
  csvFormatRow: ??(n)
  csvFormatRows: ??(t)
  csvFormatValue: ??(t)
  csvParse: ??(t, n)
  csvParseRows: ??(t, n)
  cubehelix: ??(t, n, e, r)
  cumsum: ??(t, n)
  curveBasis: ??(t)
  curveBasisClosed: ??(t)
  curveBasisOpen: ??(t)
  curveBumpX: ??(t)
  curveBumpY: ??(t)
  curveBundle: ??(t)
  curveCardinal: ??(t)
  curveCardinalClosed: ??(t)
  curveCardinalOpen: ??(t)
  curveCatmullRom: ??(t)
  curveCatmullRomClosed: ??(t)
  curveCatmullRomOpen: ??(t)
  curveLinear: ??(t)
  curveLinearClosed: ??(t)
  curveMonotoneX: ??(t)
  curveMonotoneY: ??(t)
  curveNatural: ??(t)
  curveStep: ??(t)
  curveStepAfter: ??(t)
  curveStepBefore: ??(t)
  descending: ??(t, n)
  deviation: ??(t, n)
  difference: ??(???)
  disjoint: ??(t, n)
  dispatch: ??()
  drag: ??()
  dragDisable: ??(t)
  dragEnable: ??(t, n)
  dsv: ??(t, n, e, r)
  dsvFormat: ??(t)
  easeBack: ??(t)
  easeBackIn: ??(t)
  easeBackInOut: ??(t)
  easeBackOut: ??(t)
  easeBounce: ??(t)
  easeBounceIn: ??(t)
  easeBounceInOut: ??(t)
  easeBounceOut: ??(t)
  easeCircle: ??(t)
  easeCircleIn: ??(t)
  easeCircleInOut: ??(t)
  easeCircleOut: ??(t)
  easeCubic: ??(???)
  easeCubicIn: ??(t)
  easeCubicInOut: ??(???)
  easeCubicOut: ??(t)
  easeElastic: ??(t)
  easeElasticIn: ??(t)
  easeElasticInOut: ??(t)
  easeElasticOut: ??(t)
  easeExp: ??(t)
  easeExpIn: ??(t)
  easeExpInOut: ??(t)
  easeExpOut: ??(t)
  easeLinear: ??(t)
  easePoly: ??(t)
  easePolyIn: ??(t)
  easePolyInOut: ??(t)
  easePolyOut: ??(t)
  easeQuad: ??(t)
  easeQuadIn: ??(t)
  easeQuadInOut: ??(t)
  easeQuadOut: ??(t)
  easeSin: ??(t)
  easeSinIn: ??(t)
  easeSinInOut: ??(t)
  easeSinOut: ??(t)
  every: ??(t, n)
  extent: ??(t, n)
  fcumsum: ??(t, n)
  filter: ??(t, n)
  forceCenter: ??(t, n)
  forceCollide: ??(t)
  forceLink: ??(t)
  forceManyBody: ??()
  forceRadial: ??(t, n, e)
  forceSimulation: ??(t)
  forceX: ??(t)
  forceY: ??(t)
  formatDefaultLocale: ??(n)
  formatLocale: ??(t)
  formatSpecifier: ??(t)
  fsum: ??(t, n)
  geoAlbers: ??()
  geoAlbersUsa: ??()
  geoArea: ??(t)
  geoAzimuthalEqualArea: ??()
  geoAzimuthalEqualAreaRaw: ??(n, e)
  geoAzimuthalEquidistant: ??()
  geoAzimuthalEquidistantRaw: ??(n, e)
  geoBounds: ??(t)
  geoCentroid: ??(t)
  geoCircle: ??()
  geoClipAntimeridian: ??(i)
  geoClipCircle: ??(t)
  geoClipExtent: ??()
  geoClipRectangle: ??(t, n, e, r)
  geoConicConformal: ??()
  geoConicConformalRaw: ??(t, n)
  geoConicEqualArea: ??()
  geoConicEqualAreaRaw: ??(t, n)
  geoConicEquidistant: ??()
  geoConicEquidistantRaw: ??(t, n)
  geoContains: ??(t, n)
  geoDistance: ??(t, n)
  geoEqualEarth: ??()
  geoEqualEarthRaw: ??(t, n)
  geoEquirectangular: ??()
  geoEquirectangularRaw: ??(t, n)
  geoGnomonic: ??()
  geoGnomonicRaw: ??(t, n)
  geoGraticule: ??()
  geoGraticule10: ??()
  geoIdentity: ??()
  geoInterpolate: ??(t, n)
  geoLength: ??(t)
  geoMercator: ??()
  geoMercatorRaw: ??(t, n)
  geoNaturalEarth1: ??()
  geoNaturalEarth1Raw: ??(t, n)
  geoOrthographic: ??()
  geoOrthographicRaw: ??(t, n)
  geoPath: ??(t, n)
  geoProjection: ??(t)
  geoProjectionMutator: ??(t)
  geoRotation: ??(t)
  geoStereographic: ??()
  geoStereographicRaw: ??(t, n)
  geoStream: ??(t, n)
  geoTransform: ??(t)
  geoTransverseMercator: ??()
  geoTransverseMercatorRaw: ??(t, n)
  gray: ??(t, n)
  greatest: ??(???)
  greatestIndex: ??(???)
  group: ??(???)
  groupSort: ??(t, e, r)
  groups: ??(???)
  hcl: ??(t, n, e, r)
  hierarchy: ??(t, n)
  histogram: ??()
  hsl: ??(t, n, e, r)
  html: ??(n, e)
  image: ??(t, n)
  index: ??(???)
  indexes: ??(???)
  interpolate: ??(t, n)
  interpolateArray: ??(t, n)
  interpolateBasis: ??(t)
  interpolateBasisClosed: ??(t)
  interpolateBlues: ??(t)
  interpolateBrBG: ??(t)
  interpolateBuGn: ??(t)
  interpolateBuPu: ??(t)
  interpolateCividis: ??(t)
  interpolateCool: ??(t)
  interpolateCubehelix: ??(n, r)
  interpolateCubehelixDefault: ??(t)
  interpolateCubehelixLong: ??(n, r)
  interpolateDate: ??(t, n)
  interpolateDiscrete: ??(t)
  interpolateGnBu: ??(t)
  interpolateGreens: ??(t)
  interpolateGreys: ??(t)
  interpolateHcl: ??(n, e)
  interpolateHclLong: ??(n, e)
  interpolateHsl: ??(n, e)
  interpolateHslLong: ??(n, e)
  interpolateHue: ??(t, n)
  interpolateInferno: ??(e)
  interpolateLab: ??(t, n)
  interpolateMagma: ??(e)
  interpolateNumber: ??(t, n)
  interpolateNumberArray: ??(t, n)
  interpolateObject: ??(t, n)
  interpolateOrRd: ??(t)
  interpolateOranges: ??(t)
  interpolatePRGn: ??(t)
  interpolatePiYG: ??(t)
  interpolatePlasma: ??(e)
  interpolatePuBu: ??(t)
  interpolatePuBuGn: ??(t)
  interpolatePuOr: ??(t)
  interpolatePuRd: ??(t)
  interpolatePurples: ??(t)
  interpolateRainbow: ??(t)
  interpolateRdBu: ??(t)
  interpolateRdGy: ??(t)
  interpolateRdPu: ??(t)
  interpolateRdYlBu: ??(t)
  interpolateRdYlGn: ??(t)
  interpolateReds: ??(t)
  interpolateRgb: ??(t, n)
  interpolateRgbBasis: ??(n)
  interpolateRgbBasisClosed: ??(n)
  interpolateRound: ??(t, n)
  interpolateSinebow: ??(t)
  interpolateSpectral: ??(t)
  interpolateString: ??(t, n)
  interpolateTransformCss: ??(o, a)
  interpolateTransformSvg: ??(o, a)
  interpolateTurbo: ??(t)
  interpolateViridis: ??(e)
  interpolateWarm: ??(t)
  interpolateYlGn: ??(t)
  interpolateYlGnBu: ??(t)
  interpolateYlOrBr: ??(t)
  interpolateYlOrRd: ??(t)
  interpolateZoom: ??(t, i)
  interrupt: ??(t, n)
  intersection: ??(???)
  interval: ??(t, n, e)
  isoFormat: ??(t)
  isoParse: ??(t)
  json: ??(t, n)
  lab: ??(t, n, e, r)
  lch: ??(t, n, e, r)
  least: ??(???)
  leastIndex: ??(???)
  line: ??(t, n)
  lineRadial: ??()
  linkHorizontal: ??()
  linkRadial: ??()
  linkVertical: ??()
  local: ??()
  map: ??(t, n)
  matcher: ??(t)
  max: ??(t, n)
  maxIndex: ??(t, n)
  mean: ??(t, n)
  median: ??(t, n)
  merge: ??(t)
  min: ??(t, n)
  minIndex: ??(???)
  namespace: ??(t)
  namespaces: Object {svg: "http://www.w3.org/2000/svg", xhtml: "http://www.w3.org/1999/xhtml", xlink: "http://www.w3.org/1999/xlink", xml: "http://www.w3.org/XML/1998/namespace", xmlns: "http://www.w3.org/2000/xmlns/"}
  nice: ??(t, n, e)
  now: ??()
  pack: ??()
  packEnclose: ??(t)
  packSiblings: ??(t)
  pairs: ??(???)
  partition: ??()
  path: ??()
  permute: ??(t, n)
  pie: ??()
  piecewise: ??(t, n)
  pointRadial: ??(t, n)
  pointer: ??(t, n)
  pointers: ??(t, n)
  polygonArea: ??(t)
  polygonCentroid: ??(t)
  polygonContains: ??(t, n)
  polygonHull: ??(t)
  polygonLength: ??(t)
  precisionFixed: ??(t)
  precisionPrefix: ??(t, n)
  precisionRound: ??(t, n)
  quadtree: ??(t, n, e)
  quantile: ??(t, n, e)
  quantileSorted: ??(???)
  quantize: ??(t, n)
  quickselect: ??(???)
  radialArea: ??()
  radialLine: ??()
  randomBates: ??(t)
  randomBernoulli: ??(t)
  randomBeta: ??(t, n)
  randomBinomial: ??(t, n)
  randomCauchy: ??(t, e)
  randomExponential: ??(t)
  randomGamma: ??(t, r)
  randomGeometric: ??(t)
  randomInt: ??(t, e)
  randomIrwinHall: ??(t)
  randomLcg: ??(???)
  randomLogNormal: ??()
  randomLogistic: ??(t, e)
  randomNormal: ??(t, e)
  randomPareto: ??(t)
  randomPoisson: ??(t)
  randomUniform: ??(t, e)
  randomWeibull: ??(t, e, r)
  range: ??(t, n, e)
  reduce: ??(t, n, e)
  reverse: ??(t)
  rgb: ??(t, n, e, r)
  ribbon: ??()
  ribbonArrow: ??()
  rollup: ??(???)
  rollups: ??(???)
  scaleBand: ??()
  scaleDiverging: ??()
  scaleDivergingLog: ??()
  scaleDivergingPow: ??()
  scaleDivergingSqrt: ??()
  scaleDivergingSymlog: ??()
  scaleIdentity: ??(n)
  scaleImplicit: Symbol(implicit)
  scaleLinear: ??()
  scaleLog: ??()
  scaleOrdinal: ??()
  scalePoint: ??()
  scalePow: ??()
  scaleQuantile: ??()
  scaleQuantize: ??()
  scaleRadial: ??()
  scaleSequential: ??()
  scaleSequentialLog: ??()
  scaleSequentialPow: ??()
  scaleSequentialQuantile: ??()
  scaleSequentialSqrt: ??()
  scaleSequentialSymlog: ??()
  scaleSqrt: ??()
  scaleSymlog: ??()
  scaleThreshold: ??()
  scaleTime: ??()
  scaleUtc: ??()
  scan: ??(t, n)
  schemeAccent: Array(8) ["#7fc97f", "#beaed4", "#fdc086", "#ffff99", "#386cb0", "#f0027f", "#bf5b17", "#666666"]
  schemeBlues: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeBrBG: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeBuGn: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeBuPu: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeCategory10: Array(10) ["#1f77b4", "#ff7f0e", "#2ca02c", "#d62728", "#9467bd", "#8c564b", "#e377c2", "#7f7f7f", "#bcbd22", "#17becf"]
  schemeDark2: Array(8) ["#1b9e77", "#d95f02", "#7570b3", "#e7298a", "#66a61e", "#e6ab02", "#a6761d", "#666666"]
  schemeGnBu: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeGreens: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeGreys: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeOrRd: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeOranges: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePRGn: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePaired: Array(12) ["#a6cee3", "#1f78b4", "#b2df8a", "#33a02c", "#fb9a99", "#e31a1c", "#fdbf6f", "#ff7f00", "#cab2d6", "#6a3d9a", "#ffff99", "#b15928"]
  schemePastel1: Array(9) ["#fbb4ae", "#b3cde3", "#ccebc5", "#decbe4", "#fed9a6", "#ffffcc", "#e5d8bd", "#fddaec", "#f2f2f2"]
  schemePastel2: Array(8) ["#b3e2cd", "#fdcdac", "#cbd5e8", "#f4cae4", "#e6f5c9", "#fff2ae", "#f1e2cc", "#cccccc"]
  schemePiYG: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePuBu: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePuBuGn: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePuOr: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemePuRd: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemePurples: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeRdBu: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdGy: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdPu: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeRdYlBu: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeRdYlGn: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeReds: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeSet1: Array(9) ["#e41a1c", "#377eb8", "#4daf4a", "#984ea3", "#ff7f00", "#ffff33", "#a65628", "#f781bf", "#999999"]
  schemeSet2: Array(8) ["#66c2a5", "#fc8d62", "#8da0cb", "#e78ac3", "#a6d854", "#ffd92f", "#e5c494", "#b3b3b3"]
  schemeSet3: Array(12) ["#8dd3c7", "#ffffb3", "#bebada", "#fb8072", "#80b1d3", "#fdb462", "#b3de69", "#fccde5", "#d9d9d9", "#bc80bd", "#ccebc5", "#ffed6f"]
  schemeSpectral: Array(12) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9), Array(10), Array(11)]
  schemeTableau10: Array(10) ["#4e79a7", "#f28e2c", "#e15759", "#76b7b2", "#59a14f", "#edc949", "#af7aa1", "#ff9da7", "#9c755f", "#bab0ab"]
  schemeYlGn: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlGnBu: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlOrBr: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  schemeYlOrRd: Array(10) [empty ?? 3, Array(3), Array(4), Array(5), Array(6), Array(7), Array(8), Array(9)]
  select: ??(t)
  selectAll: ??(t)
  selection: ??()
  selector: ??(t)
  selectorAll: ??(t)
  shuffle: ??(???)
  shuffler: ??(t)
  some: ??(t, n)
  sort: ??(???)
  stack: ??()
  stackOffsetDiverging: ??(t, n)
  stackOffsetExpand: ??(t, n)
  stackOffsetNone: ??(t, n)
  stackOffsetSilhouette: ??(t, n)
  stackOffsetWiggle: ??(t, n)
  stackOrderAppearance: ??(???)
  stackOrderAscending: ??(t)
  stackOrderDescending: ??(t)
  stackOrderInsideOut: ??(t)
  stackOrderNone: ??(t)
  stackOrderReverse: ??(t)
  stratify: ??()
  style: ??(t, n)
  subset: ??(t, n)
  sum: ??(t, n)
  superset: ??(t, n)
  svg: ??(n, e)
  symbol: ??(t, n)
  symbolCircle: Object {draw: ??(t, n)}
  symbolCross: Object {draw: ??(t, n)}
  symbolDiamond: Object {draw: ??(t, n)}
  symbolSquare: Object {draw: ??(t, n)}
  symbolStar: Object {draw: ??(t, n)}
  symbolTriangle: Object {draw: ??(t, n)}
  symbolWye: Object {draw: ??(t, n)}
  symbols: Array(7) [Object, Object, Object, Object, Object, Object, Object]
  text: ??(t, n)
  thresholdFreedmanDiaconis: ??(t, n, e)
  thresholdScott: ??(t, n, e)
  thresholdSturges: ??(t)
  tickFormat: ??(n, e, r, i)
  tickIncrement: ??(t, n, e)
  tickStep: ??(t, n, e)
  ticks: ??(t, n, e)
  timeDay: ??(n)
  timeDays: ??(e, r, o)
  timeFormatDefaultLocale: ??(n)
  timeFormatLocale: ??(t)
  timeFriday: ??(n)
  timeFridays: ??(e, r, o)
  timeHour: ??(n)
  timeHours: ??(e, r, o)
  timeInterval: ??(t, n, e, r)
  timeMillisecond: ??(n)
  timeMilliseconds: ??(e, r, o)
  timeMinute: ??(n)
  timeMinutes: ??(e, r, o)
  timeMonday: ??(n)
  timeMondays: ??(e, r, o)
  timeMonth: ??(n)
  timeMonths: ??(e, r, o)
  timeSaturday: ??(n)
  timeSaturdays: ??(e, r, o)
  timeSecond: ??(n)
  timeSeconds: ??(e, r, o)
  timeSunday: ??(n)
  timeSundays: ??(e, r, o)
  timeThursday: ??(n)
  timeThursdays: ??(e, r, o)
  timeTickInterval: ??(n, r, i)
  timeTicks: ??(t, n, e)
  timeTuesday: ??(n)
  timeTuesdays: ??(e, r, o)
  timeWednesday: ??(n)
  timeWednesdays: ??(e, r, o)
  timeWeek: ??(n)
  timeWeeks: ??(e, r, o)
  timeYear: ??(n)
  timeYears: ??(e, r, o)
  timeout: ??(t, n, e)
  timer: ??(t, n, e)
  timerFlush: ??()
  transition: ??(t)
  transpose: ??(t)
  tree: ??()
  treemap: ??()
  treemapBinary: ??(t, n, e, r, i)
  treemapDice: ??(t, n, e, r, i)
  treemapResquarify: ??(t, e, r, i, o)
  treemapSlice: ??(t, n, e, r, i)
  treemapSliceDice: ??(t, n, e, r, i)
  treemapSquarify: ??(t, e, r, i, o)
  tsv: ??(n, e, r)
  tsvFormat: ??(n, e)
  tsvFormatBody: ??(t, n)
  tsvFormatRow: ??(n)
  tsvFormatRows: ??(t)
  tsvFormatValue: ??(t)
  tsvParse: ??(t, n)
  tsvParseRows: ??(t, n)
  union: ??(???)
  utcDay: ??(n)
  utcDays: ??(e, r, o)
  utcFriday: ??(n)
  utcFridays: ??(e, r, o)
  utcHour: ??(n)
  utcHours: ??(e, r, o)
  utcMillisecond: ??(n)
  utcMilliseconds: ??(e, r, o)
  utcMinute: ??(n)
  utcMinutes: ??(e, r, o)
  utcMonday: ??(n)
  utcMondays: ??(e, r, o)
  utcMonth: ??(n)
  utcMonths: ??(e, r, o)
  utcSaturday: ??(n)
  utcSaturdays: ??(e, r, o)
  utcSecond: ??(n)
  utcSeconds: ??(e, r, o)
  utcSunday: ??(n)
  utcSundays: ??(e, r, o)
  utcThursday: ??(n)
  utcThursdays: ??(e, r, o)
  utcTickInterval: ??(n, r, i)
  utcTicks: ??(t, n, e)
  utcTuesday: ??(n)
  utcTuesdays: ??(e, r, o)
  utcWednesday: ??(n)
  utcWednesdays: ??(e, r, o)
  utcWeek: ??(n)
  utcWeeks: ??(e, r, o)
  utcYear: ??(n)
  utcYears: ??(e, r, o)
  variance: ??(t, n)
  version: "6.7.0"
  window: ??(t)
  xml: ??(n, e)
  zip: ??()
  zoom: ??()
  zoomIdentity: tx {k: 1, x: 0, y: 0}
  zoomTransform: ??(t)
}
d3 = require("d3@6")
