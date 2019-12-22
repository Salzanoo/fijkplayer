# fijkplayer (Video player plugin for Flutter) Flutter 


A Flutter media player plugin for iOS and android based on [ijkplayer](https://github.com/befovy/ijkplayer)

## Documentation

* Development Documentation https://fijkplayer.befovy.com/docs/en/ quick start、guide、and concepts about fijkplayer 
* https://fijkplayer.befovy.com/docs/zh/ fijkplayer
* dart api https://pub.dev/documentation/fijkplayer/ detail API and argument explaination
* Release Notes https://github.com/befovy/fijkplayer/releases and [CHANGELOG.md](./CHANGELOG.md)
* FAQ https://fijkplayer.befovy.com/docs/zh/faq.html

## Installation 

Add `fijkplayer` as a [dependency in your pubspec.yaml file](https://flutter.io/using-packages/). 

```yaml
dependencies:
  fijkplayer: ^0.2.3
```

Use git branch which not published to pub.
```yaml
dependencies:
  fijkplayer:
    git:
      url: https://github.com/salzanoo/fijkplayer.git
      ref: develop # can be replaced to branch or tag name
```

## Example

```dart
import 'package:fijkplayer/fijkplayer.dart';
import 'package:flutter/material.dart';

class VideoScreen extends StatefulWidget {
  final String url;

  VideoScreen({@required this.url});

  @override
  _VideoScreenState createState() => _VideoScreenState();
}

class _VideoScreenState extends State<VideoScreen> {
  final FijkPlayer player = FijkPlayer();

  _VideoScreenState();

  @override
  void initState() {
    super.initState();
    player.setDataSource(widget.url, autoPlay: true);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(title: Text("Fijkplayer Example")),
        body: Container(
          alignment: Alignment.center,
          child: FijkView(
            player: player,
          ),
        ));
  }

  @override
  void dispose() {
    super.dispose();
    player.release();
  }
}

```

## Already in use in following apps
Contact me or create pull request to add your app here.

## Contributors

Thanks goes to [these wonderful people](./CONTRIBUTORS.md) ([emoji key](https://allcontributors.org/docs/en/emoji-key))

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome

## iOS Warning

Warning: The fijkplayer video player plugin is not functional on iOS simulators. An iOS device must be used during development/testing. For more details, please refer to this [issue](https://github.com/flutter/flutter/issues/14647).


## Next Plan 

See the development plan of next version in https://github.com/befovy/fijkplayer/projects/2
