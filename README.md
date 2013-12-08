FLAC-PHP
========

Class for native reading FLAC's meta data.


Edit on 8th December 2013 by François LASSERRE <choiz@me.com>
- Add average bitrate and filesize

Example
-------

```php
<?php
require('flac.php');

header('Content-Type: text/plain;charset=utf-8');

$t = microtime(true);
$flac = new Flac('mySong.flac');
echo 'Meta-Blocks: '; print_r($flac->streamMetaBlocks); echo "\n";
echo 'Sample Rate: '.$flac->streamSampleRate."\n";
echo 'Channels: '.$flac->streamChannels."\n";
echo 'Bits per sample: '.$flac->streamBitsPerSample."\n";
echo 'Total samples: '.$flac->streamTotalSamples."\n";
echo 'Duration: '.$flac->streamDuration."\n";
echo 'Average Bitrate: '.$flac->averageBitrate."\n";
echo 'Filesize: '.$flac->filesize."\n";
echo 'MD5 checksum (audio data): '.$flac->streamMd5."\n";
echo 'Vorbis-Comment: ';nl2br(print_r($flac->vorbisComment)); echo "\n\n";
echo 'runtime: '.(microtime(true) - $t).'s';
```

Return:
-------

```php
Meta-Blocks: Array
(
    [0] => 1
    [1] => 1
    [2] => 0
    [3] => 1
    [4] => 1
    [5] => 0
    [6] => 0
)

Sample Rate: 96000
Channels: 2
Bits per sample: 24
Total samples: 15775105
Duration: 164
Average Bitrate: 2740.3686829268
Filesize: 56177558
MD5 checksum (audio data): d927bbf76c9faaa9b96b4ffefcfcb366
Vorbis-Comment: Array
(
    [vendorLength] => 32
    [vendorString] => reference libFLAC 1.2.1 20070917
    [comments] => Array
        (
            [ensemble] => Array
                (
                    [0] => Daft Punk
                )

            [tracknumber] => Array
                (
                    [0] => A1
                )

            [title] => Array
                (
                    [0] => Daftendirekt
                )

            [album] => Array
                (
                    [0] => Homework
                )

            [artist] => Array
                (
                    [0] => Daft Punk
                )

            [genre] => Array
                (
                    [0] => House
                )

            [date] => Array
                (
                    [0] => 1997
                )

        )

)
```