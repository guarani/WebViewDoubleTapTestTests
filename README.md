In the UIWebView, if an input element containing text has focus, and a button is pressed
that causes the input to lose focus, then subsequently double-tapping on the input to 
regain foucus and selecting Cut (or Copy or Paste) from the popup bar that appears causes
the UIWebView to crash with the error

	-[UIWebView cut:]: unrecognized selector sent to instance 0x10900ca60


This is the stack trace:

2014-01-23 15:11:08.352 WebViewDoubleTapTest[8416:70b] -[UIWebView cut:]: unrecognized selector sent to instance 0x10900ca60
2014-01-23 15:11:08.361 WebViewDoubleTapTest[8416:70b] *** Terminating app due to uncaught exception 'NSInvalidArgumentException', reason: '-[UIWebView cut:]: unrecognized selector sent to instance 0x10900ca60'
*** First throw call stack:
(
	0   CoreFoundation                      0x000000010188d795 __exceptionPreprocess + 165
	1   libobjc.A.dylib                     0x00000001015f0991 objc_exception_throw + 43
	2   CoreFoundation                      0x000000010191ebad -[NSObject(NSObject) doesNotRecognizeSelector:] + 205
	3   CoreFoundation                      0x000000010187f09d ___forwarding___ + 973
	4   CoreFoundation                      0x000000010187ec48 _CF_forwarding_prep_0 + 120
	5   UIKit                               0x000000010059b4fd -[UICalloutBar buttonPressed:] + 290
	6   Foundation                          0x00000001011db1cc __NSFireDelayedPerform + 354
	7   CoreFoundation                      0x000000010184fe24 __CFRUNLOOP_IS_CALLING_OUT_TO_A_TIMER_CALLBACK_FUNCTION__ + 20
	8   CoreFoundation                      0x000000010184f9a2 __CFRunLoopDoTimer + 962
	9   CoreFoundation                      0x000000010183896e __CFRunLoopRun + 1614
	10  CoreFoundation                      0x0000000101837f33 CFRunLoopRunSpecific + 467
	11  GraphicsServices                    0x00000001039943a0 GSEventRunModal + 161
	12  UIKit                               0x0000000100253043 UIApplicationMain + 1010
	13  WebViewDoubleTapTest                0x0000000100001ec3 main + 115
	14  libdyld.dylib                       0x0000000101f1c5fd start + 1
	15  ???                                 0x0000000000000001 0x0 + 1
)
libc++abi.dylib: terminating with uncaught exception of type NSException
