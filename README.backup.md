# Nobo
"Nobo" means "No Borders", also means "登る" in Japanese.

**Nobo** is a spider that you could get your data from each service provides by Ritsumeikan Univ.

You can use **Nobo** to build your API with many frameworks (`Flask`, `Django` etc.) under GPLv3 License.

**Nobo** is the most important part of [RitsFun back-end API](https://api.rits.fun).

# License
__GPLv3__

__注意: 商用利用の際にはご連絡願います。__

# How to use?
Install requirements with pip.

```bash
pip install -r requirements.txt
```

Use **Nobo** in your project (.py).

```python
import Nobo
```

# Manaba API
## How to use
1. Create a `manabaUser` instance.

    ```python
    # The following username and password is not real :)
    fangzhou = Nobo.manabaUser("is0000ab", "12345678")
    ```

2. Use `login()` method to log in Manaba+R.

    ```python
    fangzhou.login()
    ```

3. Use `getCourseList()` method to get all courses information.

    ```python
    fangzhou.getCourseList()
    ```
    
4. Use `outputJSON("<ouputFileName>")` method to save data as JSON format.

    ```python
    fangzhou.outputJSON("temp.json")
    ```

## Example manaba data
The example course will show as following.

```json
[
    {
        "basic": [
            {
                "name": "(留)日本語Ⅷ(キャリア日本語b)",
                "code": 30819,
                "class": "G1"
            },
            {
                "name": "(留)日本語ⅩⅡ 口頭表現",
                "code": "30993",
                "class": "G1"
            }
        ],
        "teacher": [
            "久米 朋子"
        ],
        "time": {
            "year": 2017,
            "semester": "fall",
            "weekday": "Monday",
            "period": "2"
        },
        "campus": "BKC",
        "room": "アドセミナリオ309号教室"
    },
   
    {
        ...
        other courses
        ...
    }
]
```

# Syllabus API
## How to use
1. Create a `syllabusUser` instance.

    ```python
    # The following username and password is not real :)
    fangzhou = Nobo.syllabusUser("is0000ab", "12345678")
    ```

2. Use `login()` method to log in Syllabus.

    ```python
    fangzhou.login()
    ```

3. Use `getSyllabusById(<courseYear>, <courseID>)` method to get all courses information.

    ```python
    fangzhou.getSyllabusById(2017, 33294)
    ```
    
4. Use `outputJSON("<ouputFileName>")` method to save data as JSON format.

    ```python
    fangzhou.outputJSON("temp.json")
    ```
    
## Example syllabus data
The example course will show as following.

```json
{
    "basic": [
        {
            "name": "知能情報処理演習2",
            "class": "D3"
        },
        {
            "name": "知能情報システム創成2",
            "class": "D3"
        }
    ],
    "time": {
        "year": 2017,
        "semester": "fall",
        "weekday": "Monday",
        "period_art": "3",
        "period_sci": "5-6"
    },
    "teacher": [
        "井本 桂右",
        "原田 智広"
    ],
    "credit": 2,
    "outline": "本科目は，計算知能，機械知能，生体知能を３本柱とする知能情報学科にあって，特に計算知能分野の実験・演習系科目の集大成であり，「知能情報処理演習１」や「知能情報システム創成」で修得した技術を基盤に，さらに発展した知能情報処理技術を学ぶ．C言語によるプログラミング演習課題として，最適化・探索プログラミング，および，画像処理プログラミングの２テーマに各７週間かけて取り組む．いずれのテーマにおいても教員とティーチングアシスタントの指導や補助の下で，各人の課題設定能力，問題解決能力，考察・報告・発表能力を高め，卒業研究への準備とする．",
    "objectives": "最適化・探索プログラミングでは，遺伝的アルゴリズムなどに代表される最適化メタヒューリスティクスの概要を学び，最適化問題を解くCプログラミングに取り組む．知能システムの構築に向けた要素技術に触れ，アルゴリズムの実装，個別課題への適用における考察や問題解決の各能力を高める．\n画像処理プログラミングでは，二値化，エッジ検出，パターンマッチングなどの，デジタル画像処理のための基本アルゴリズムのCプログラミング に取り組む.",
    "precourse": "履修しておくことが望まれる科目：プログラミング演習１・２，知能情報処理演習１，知能情報システム創成，知能情報学実験Ⅰ（但し，本科目と同時期に開講），確率統計Ｄ，センシング工学（但し，本科目と同時期に開講），人工知能概論（但し，本科目と同時期に開講），画像認識・理解（但し，本科目と同時期に開講）本科目の履修を前提とする科目：知能システム，卒業研究１・２・３",
    "schedule": [
        {
            "lecture": 1,
            "theme": "導入と解説",
            "references": "両テーマの概要と資料説明"
        },
        {
            "lecture": 2,
            "theme": "最適化・探索プログラミング(1)",
            "references": "進化型計算の基礎，単純GAのアルゴリズム"
        },
        {
            "lecture": 3,
            "theme": "最適化・探索プログラミング(2)",
            "references": "最適化問題，厳密解法・ヒューリスティクス・メタヒューリスティクス"
        },
        {
            "lecture": 4,
            "theme": "最適化・探索プログラミング(3)",
            "references": "遺伝演算子，パラメータ空間，数値実験での比較"
        },
        {
            "lecture": 5,
            "theme": "最適化・探索プログラミング(4)",
            "references": "中間レポート提出と講評，ナップザック問題，ペナルティ法"
        },
        {
            "lecture": 6,
            "theme": "最適化・探索プログラミング(5)",
            "references": "欲張り法，ヒューリスティクス・デコーディング"
        },
        {
            "lecture": 7,
            "theme": "最適化・探索プログラミング(6)",
            "references": "発展課題，多目的最適化・複数の拘束条件"
        },
        {
            "lecture": 8,
            "theme": "最適化・探索プログラミング(7)",
            "references": "最終レポート提出と講評，まとめ"
        },
        {
            "lecture": 9,
            "theme": "画像処理プログラミング(1)",
            "references": "カラー画像の濃淡化"
        },
        {
            "lecture": 10,
            "theme": "画像処理プログラミング(2)",
            "references": "ヒストグラム生成，二値化"
        },
        {
            "lecture": 11,
            "theme": "画像処理プログラミング(3)",
            "references": "統計的画像処理"
        },
        {
            "lecture": 12,
            "theme": "画像処理プログラミング(4)",
            "references": "微分フィルタリング，エッジ検出"
        },
        {
            "lecture": 13,
            "theme": "画像処理プログラミング(5)",
            "references": "微分フィルタリング，エッジ検出"
        },
        {
            "lecture": 14,
            "theme": "画像処理プログラミング(6)",
            "references": "パターン，パターンマッチング，パターン検出"
        },
        {
            "lecture": 15,
            "theme": "画像処理プログラミング(7)",
            "references": "パターン，パターンマッチング，パターン検出"
        }
    ],
    "recommendation": "授業時間以外に，演習室を利用して，演習課題に関する質問に個別対応するfollow up時間を設定する．",
    "grade_evluation": {
        "note": "両テーマの合格，および，各テーマの授業回数のそれぞれ2／3以上の出席が本科目合格のための「必要条件」です．その上で，両テーマの評価を総合的に判断し，100点満点の60点以上を合格とします．",
        "data": [
            {
                "type": "End of Semester Examination (Written)",
                "percentage": 0,
                "note": ""
            },
            {
                "type": "Report Examination",
                "percentage": 0,
                "note": ""
            },
            {
                "type": "Other",
                "percentage": 100,
                "note": "最適化・探索プログラミングレポート評価 30%画像処理プログラミング評価 30%出席評価 20%授業取り組み評価 20%"
            }
        ]
    },
    "advice": "受講者は，通常の講義課目とは違うことを十分に認識して，事前の準備や復習を十分に行い，follow up時間も利用して，課題に対して主体的に責任をもって取り組むことが必要である．",
    "text_books": {
        "note": "第１回授業において，課題テキストを配布する．",
        "book": []
    },
    "ref_books": {
        "note": "配布資料に参考文献として記載，あるいは授業中に随時紹介する．",
        "book": []
    },
    "ref_pages": "授業支援サイト http://www.ice.ci.ritsumei.ac.jp/~ruck/CLASSES/eic2.htm\n最適化・探索プログラミング http://www.sys.ci.ritsumei.ac.jp/sousei2-ga/",
    "contact_methods": [
        "学生との直接対話"
    ],
    "other_comments": ""
}
```
