This is a simple timer implemented by rxjava2.

I copy this class into all the little apps I make. I'm tired of doing it. Now it's a library.


Usage
-----

```java
timer = Rx2Timer.builder()
                .initialDelay(0) //default is 0
                .period(1) //default is 1
                .take(30) //default is 60
                .unit(TimeUnit.SECONDS) // default is TimeUnit.SECONDS
                .onCount(count -> {
                    if (count < 10) {
                        binding.text.setText("0" + count + " s");
                    } else {
                        binding.text.setText(count + " s");
                    }
                })
                .onError(e -> binding.text.setText(R.string.count))
                .onComplete(() -> binding.text.setText(R.string.count))
                .build();

timer.start();
timer.stop();
timer.restart();
timer.pause();
timer.resume();
                
```

Download
--------

```groovy
compile 'com.github.thepacific:rx2timer:0.0.1'
```

Snapshots of the development version are available in [Sonatype's `snapshots` repository][snap].


License
-------

[The MIT License ](https://opensource.org/licenses/MIT)
