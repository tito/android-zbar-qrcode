Android/Kivy Qrcode scanner
===========================

Author: Mathieu Virbel <mat@meltingrocks.com>

Featuring:

- Android camera initialization
- Show the android camera into a Android surface that act as an overlay
- New AndroidWidgetHolder that control any android view as an overlay
- New ZbarQrcodeDetector that use AndroidCamera / PreviewFrame + zbar to
  detect Qrcode.

Usage
-----

	def on_symbol(detector, symbols):
		print 'found', len(symbols), 'symbols'
		for symbol in symbols:
			print '- qrcode: {}'.format(symbol.data)

		# stop the detector if we found a symbol.
		# don't if you want continuous detection.
		detector.stop()

	detector = ZbarQrcodeDetector()
	detector.bind(symbols=on_symbols)


Compile
-------

Use buildozer:

	buildozer android debug deploy run
