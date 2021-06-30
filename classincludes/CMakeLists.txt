set (class_headers
  QwtAbstractScaleDraw
  QwtAlphaColorMap
  QwtAxis
  QwtAxisId
  QwtBezier
  QwtClipper
  QwtColorMap
  QwtColumnRect
  QwtColumnSymbol
  QwtDate
  QwtDateScaleDraw
  QwtDateScaleEngine
  QwtDynGridLayout
  QwtGlobal
  QwtGraphic
  QwtHueColorMap
  QwtInterval
  QwtIntervalSymbol
  QwtLinearColorMap
  QwtLinearScaleEngine
  QwtLogScaleEngine
  QwtLogTransform
  QwtMagnifier
  QwtMath
  QwtNullPaintDevice
  QwtNullTransform
  QwtPainter
  QwtPainterCommand
  QwtPanner
  QwtPicker
  QwtPickerClickPointMachine
  QwtPickerClickRectMachine
  QwtPickerDragLineMachine
  QwtPickerDragPointMachine
  QwtPickerDragRectMachine
  QwtPickerMachine
  QwtPickerPolygonMachine
  QwtPickerTrackerMachine
  QwtPixelMatrix
  QwtPlainTextEngine
  QwtPoint3D
  QwtPointPolar
  QwtPowerTransform
  QwtRichTextEngine
  QwtRoundScaleDraw
  QwtSaturationValueColorMap
  QwtScaleArithmetic
  QwtScaleDiv
  QwtScaleDraw
  QwtScaleEngine
  QwtScaleMap
  QwtSimpleCompassRose
  QwtSplineBasis
  QwtSpline
  QwtSplineC1
  QwtSplineC2
  QwtSplineCubic
  QwtSplineG1
  QwtSplineInterpolating
  QwtSplineLocal
  QwtSplineParameter
  QwtSplineParametrization
  QwtSplinePleasing
  QwtSplinePolynomial
  QwtSymbol
  QwtSystemClock
  QwtText
  QwtTextEngine
  QwtTextLabel
  QwtTransform
  QwtWidgetOverlay)

if (WITH_PLOT)
  list (APPEND class_headers
    QwtAbstractLegend
    QwtCurveFitter
    QwtEventPattern
    QwtIntervalSample
    QwtLegend
    QwtLegendData
    QwtLegendLabel
    QwtPointMapper
    QwtMatrixRasterData
    QwtOHLCSample
    QwtPlot
    QwtPlotAbstractBarChart
    QwtPlotAbstractCanvas
    QwtPlotBarChart
    QwtPlotCanvas
    QwtPlotCurve
    QwtPlotDict
    QwtPlotDirectPainter
    QwtPlotGraphicItem
    QwtPlotGrid
    QwtPlotHistogram
    QwtPlotIntervalCurve
    QwtPlotItem
    QwtPlotLayout
    QwtPlotLegendItem
    QwtPlotMagnifier
    QwtPlotMarker
    QwtPlotMultiBarChart
    QwtPlotPanner
    QwtPlotPicker
    QwtPlotRasterItem
    QwtPlotRenderer
    QwtPlotRescaler
    QwtPlotScaleItem
    QwtPlotSeriesItem
    QwtPlotShapeItem
    QwtPlotSpectroCurve
    QwtPlotSpectrogram
    QwtPlotTextLabel
    QwtPlotTradingCurve
    QwtPlotVectorField
    QwtPlotZoneItem
    QwtPlotZoomer
    QwtScaleWidget
    QwtRasterData
    QwtSeriesData
    QwtSetSample
    QwtSamplingThread
    QwtSplineCurveFitter
    QwtWeedingCurveFitter
    QwtIntervalSeriesData
    QwtPoint3DSeriesData
    QwtPointSeriesData
    QwtSetSeriesData
    QwtSyntheticPointData
    QwtPointArrayData
    QwtTradingChartData
    QwtVectorFieldSymbol
    QwtVectorFieldArrow
    QwtVectorFieldThinArrow
    QwtVectorFieldData
    QwtVectorFieldSample
    QwtCPointerData)
endif ()

if (WITH_OPENGL)
  list (APPEND class_headers QwtPlotOpenGLCanvas)
endif ()

if (WITH_WIDGETS)
  list (APPEND class_headers
    QwtAbstractSlider
    QwtAbstractScale
    QwtArrowButton
    QwtAnalogClock
    QwtCompass
    QwtCompassMagnetNeedle
    QwtCompassRose
    QwtCompassScaleDraw
    QwtCompassWindArrow
    QwtCounter
    QwtDial
    QwtDialNeedle
    QwtDialSimpleNeedle
    QwtKnob
    QwtSlider
    QwtThermo
    QwtWheel)
endif ()

if (WITH_SVG)
  list (APPEND class_headers QwtPlotSvgItem)
endif ()

install (FILES ${class_headers} DESTINATION include)
