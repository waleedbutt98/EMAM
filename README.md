# EMAM (Engineer Muhammad Ali Mirza)

Engineer Muhammad Ali Mirza is among the few Islamic scholars and researcher working towards the propagation of true Islamic principles and the unity of Muslim Ummah based on solutions from Quran and Sunnah regardless of any sect or school of thought.

According to him no sect ( Sunni, Shia, Wahabi, Deobandi, Barelvi, Ahl-e-Hadith or whatever) is completely wrong and at the same time not totally correct. There are controversies that have developed due to the scholars of the relevant sects defending their ideologies and hiding the truth from their followers. Engineer Muhammad Ali Mirza highlights and corrects these controversial issues with true references of Quran and Sahih Hadith.

Engineer Muhammad Ali Mirza does not consider any sect as Kaffir except ‘Qadiyani’ (offshoot of Sunni school of thought) and ‘Nusairi’ (offshoot of Shia school of thought).

## Official Cell No

+92-321-5900162. (Call Timings: 09:00 am to 05:00 pm).

## Official Website

[AhleSunnatPak.com](https://www.AhleSunnatPak.com)

## Official YouTube Channels

[Engineer Muhammad Ali Mirza - Official Channel](https://www.youtube.com/user/EngineerMuhammadAliM)  
[Engineer Muhammad Ali Mirza (Complete Lectures Channel)](https://www.youtube.com/user/EngrMuhammadAliMirza)

# This Repository

This is the git repository containing all the timestamps to his lectures on his youtube channel in JSON format. This API is maintained by his student ([me](https://github.com/waleedbutt98)) and is independent of EMAM entirely. This API can be used free of cost with any application and anywhere in the development.

## Usage

The [emam.json](https://github.com/waleedbutt98/EMAM/blob/master/emam.json) file contains the JSON object with keys named after lecture series. Each Lecture series then contains the timestamps according to each lecture in proper format. The format can be of two types based on two types of series.

1. Quran Classes
2. General Lectures (Mas'alah, Majlis etc.)

### 1. Quran Classes

The Quran Classes are of three types:

1. "nqc", which is short for New Quran Class or formally known as [Qura'an Asaan Tarjuma Aur Tafseer](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQIyoPcakbDO3H4Q-BGMpWK)
2. "qc", is short for Quran Class or formally known as [Qura'an Tafseer Lecture (Quran Class)](https://www.youtube.com/playlist?list=PLdC3g7t1lPKTHaO-_ZE04Z9h90oye14t-)
3. "eqc", is short for English Quran Class or fromally known as [Qur'an Easy Translation and Explaination (Quran Class)](https://www.youtube.com/playlist?list=PLdC3g7t1lPKSWbIBKtQX2bb6s1rYgopL7)

The Quran Classes are formatted in the way, where first key represents the surah number and then its child key represents the Ayat number. Then there is JSON object containing the information regarding that ayat i.e. where that ayat was discussed and mentioned.

```
"nqc": { <--- Series Name
  "1": { <--- Surah 1 Al Fatiha
    "1": { <--- Ayat 1 of Surah 1 Al Fatiha (1:1)
      "v": "2zjJbc39qc8", <--- It is the video id of YouTube lecture where this ayat is discussed.
      "lc": "UgyGvOWBWwVQn63GFZt4AaABAg", <--- It is ID of comment where the timestamps are mentioned
      "index": 7, <--- It is the number of lecture in the series
      "t": 1906 <--- It is time in seconds where the
    }
  }
}
```

### 2. General Lectures

The general lectures can be of many types. Most common are:

1. "maslah", which is [Mas'alah Series](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQlQo-qSiTsUbb5Fmv6Whm5)
2. "pqa", which is short for [Public Questions and Answer Session](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQPhJmuzpIRyd2TaFVda5ov)
3. "majlis", which is short for [ILMI-o-Tahqeeqi MAJALIS](https://www.youtube.com/playlist?list=PLdC3g7t1lPKR9C6k-mu8YZY5CYYdmPT9m)
4. "live", which is short for [Live Q & A Session With Engineer Muhammad Ali Mirza | Shahid And Bilal Official](https://www.youtube.com/playlist?list=PLdC3g7t1lPKS_Er5szzZdrNK0SUVFLDtO)
5. "critical", which contains videos of EMAM which are not part of any series.

The general lectures follow the pattern where first key represents the series. Then second key represents its number in series and then its information.

```
"pqa": { <--- Series Name
  "1": { <--- 001-Public Question & Answers Session...
    "v": "2zjJbc39qc8", <--- It is the video id of YouTube lecture.
      "lc": "UgyGvOWBWwVQn63GFZt4AaABAg", <--- It is ID of comment where the timestamps are mentioned
      "index": 1, <--- It is the number of lecture in the series
      "questions": [ <--- Array of topics in lecture with time
        {
          "t": 0, <--- Time At Which The Topic is Discussed. Compulsory, always a number
          "text": "Anything", <--- Topic which is Discussed. Compulsory, always a string
          "q": true, <--- Indicates whether it is a sub topic or question, can be undefined, true or false only
          "references": [ <--- Array of cross references referred by EMAM.
            {
              "text": "Forex Trading", <--- Video Title
              "v": "v_aG8j1vkNc" <--- YT Video ID.
            }
          ]
        }
      ]
  }
}
```

## YouTube Links

YouTube Links can be generated from above information. Lets Take example of Surah 1 Ayat 1.

- Normal Link  
  `https://youtube.com/watch?v={nqc["1"]["1"].v}&t={nqc["1"]["1"].t}`  
  Example: https://youtube.com/watch?v=2zjJbc39qc8&t=1906  

- With Comment Highlighting.  
  `https://youtube.com/watch?v={nqc["1"]["1"].v}&t={nqc["1"]["1"].t}&lc={nqc["1"]["1"].lc}`  
  Example: https://youtube.com/watch?v=2zjJbc39qc8&t=1906&lc=UgyGvOWBWwVQn63GFZt4AaABAg  

- With List, each series include a "list" value with list object that can be used to open link with playlist.  
  `https://youtube.com/watch?v={nqc["1"]["1"].v}&t={nqc["1"]["1"].t}&lc={nqc["1"]["1"].lc}&index={nqc["1"]["1"].index&list={nqc.list}}`  
  Example: https://youtube.com/watch?v=2zjJbc39qc8&t=1906&lc=UgyGvOWBWwVQn63GFZt4AaABAg&index=7&list=PLdC3g7t1lPKQIyoPcakbDO3H4Q-BGMpWK
