1. Generate font from http://en.glyphwiki.org/wiki/Group:hkcs_m
2. Run `otfccdump.exe --pretty -o hkcs-traditional-bmp-canonicalonly.json gw2011070.ttf`
3. Replace the "name" part of the JSON:
````
    "name": [
	{
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1028,
            "nameID": 1,
            "nameString": "香港民間字集 傳承字形版 (基本區-僅正字形)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1028,
            "nameID": 2,
            "nameString": "Regular"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1028,
            "nameID": 4,
            "nameString": "香港民間字集 傳承字形版 (基本區-僅正字形)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 0,
            "nameString": "Copyright © 2018 Hong Kong Character Set Project (https://github.com/hfhchan/hkcs), GlyphWiki (glyphwiki.org)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 1,
            "nameString": "HKCS Traditional Orthography (BMP-CanonicalOnly)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 2,
            "nameString": "Regular"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 3,
            "nameString": "HKCS-Traditional-BMP-CanonicalOnly;build20180123"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 4,
            "nameString": "HKCS-Traditional-BMP-CanonicalOnly"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 5,
            "nameString": "Version 2.000;build20180123"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 6,
            "nameString": "HKCS-Traditional-BMP-CanonicalOnly-Regular"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 8,
            "nameString": "Henry Chan"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 9,
            "nameString": "Henry Chan (ideographs)\n\nMultiple Contributers from GlyphWiki (alphanumerics & punctuation)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 10,
            "nameString": "Henry Chan (ideographs)\n\nMultiple Contributers from GlyphWiki (alphanumerics & punctuation)"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 11,
            "nameString": "https://github.com/hfhchan/hkcs"
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 13,
            "nameString": "This Font Software is licensed under the SIL Open Font License, Version 1.1. This Font Software is distributed on an \"AS IS\" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the SIL Open Font License for the specific language, permissions and limitations governing your use of this Font Software."
        },
        {
            "platformID": 3,
            "encodingID": 1,
            "languageID": 1033,
            "nameID": 14,
            "nameString": "http://scripts.sil.org/OFL"
        }		
    ],
````

4. Set OS/2 ulCodePageRange1 to 
````
        "ulCodePageRange1": {
            "latin1": true,
            "big5": true
        },
````

5. Run `otfccbuild.exe --keep-unicode-ranges -O3 hkcs-traditional-bmp-canonicalonly.json -o hkcs-traditional-bmp-canonicalonly.ttf
