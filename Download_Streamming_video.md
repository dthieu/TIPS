### How to download video from website without download permission:
* Use the Firefox browser
* Go to the web site containing video
* Press ctrl + shift + E --> network tab
* Select media filter only
* Press F5 for refresh web page
* Filter m3u8
* Save that file (file *.m3u8 contains a lot of link *.ts) --> add "https://" each lines
* Ex:
  ``` shell
  #EXTM3U
  #EXT-X-VERSION:5
  #EXT-X-PLAYLIST-TYPE:VOD
  #EXT-X-TARGETDURATION:3
  #EXTINF:3.000000,
  https://proxy-24.sg1.dailymotion.com/sec(s_13t_2f7O0wwaaFk-MzVah1AQ30aZwY30_ytvqIfhqrDQ--XbYPO7q5e5ubqn939bY0HKfDtsJgLmpjUD8NG03UaOsWA8xliYNYTnH-9aM)/frag(1)/video/967/449/491944769_mp4_h264_aac_hd.ts
  #EXTINF:3.000000,
  https://proxy-24.sg1.dailymotion.com/sec(s_13t_2f7O0wwaaFk-MzVah1AQ30aZwY30_ytvqIfhqrDQ--XbYPO7q5e5ubqn939bY0HKfDtsJgLmpjUD8NG03UaOsWA8xliYNYTnH-9aM)/frag(2)/video/967/449/491944769_mp4_h264_aac_hd.ts
  #EXTINF:3.000000,
  https://proxy-24.sg1.dailymotion.com/sec(s_13t_2f7O0wwaaFk-MzVah1AQ30aZwY30_ytvqIfhqrDQ--XbYPO7q5e5ubqn939bY0HKfDtsJgLmpjUD8NG03UaOsWA8xliYNYTnH-9aM)/frag(3)/video/967/449/491944769_mp4_h264_aac_hd.ts
  ...
  ```
* Now you can use ffmpeg to download video by below command:
  ``` shell
  ffmpeg -protocol_whitelist https,file,tls,tcp,crypto -i [input].m3u8 -c copy [output].mp4
  ```
