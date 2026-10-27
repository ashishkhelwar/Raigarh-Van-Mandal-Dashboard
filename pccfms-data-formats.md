# PCCFMS — How Data Is Kept (field-level reading)

**Source:** Entry pages of all 109 formats, PCCFMS portal, login रायगढ़ वनमंडल
**Read on:** 27 Oct 2026 (read-only, nothing saved or sent)

---

## 1. Common pattern (every format)

Every Entry page has the same shell:

1. **माह + वर्ष** dropdowns (the reporting period).
2. **Input block**: dropdowns (masters) + text boxes for one record.
3. **Grid below** listing saved rows for that month, with *Select / Delete*.
4. Buttons: **SAVE · Same as Last Month · निरंक · Send · Back** (some also have *Import From Master*, *Remove All*, *ADD*, *NEW*).

So the data model is a **monthly snapshot**: each month is a fresh set of rows, either re-typed or copied with *Same as Last Month*. Nothing carries forward automatically.

## 2. Five ways a row is defined

| Row = | Formats |
|---|---|
| **One division total** (single row/month) | WP-003, PR-001, PR-009, PR-010, PR-014, PR-015, PR-016, PD-001, PD-003, PD-004, PD-005, PD-006, PD-011, LS-008, BD-004, EX-003, EX-004, EX-006, JM-010, JM-014, AN-012 |
| **One row per परिक्षेत्र** (घरघोड़ा / खरसिया / रायगढ़ / तमनार; some add तमनार(उत्पादन), उर्दना डिपो) | PR-002 to PR-007, PR-012, PD-002, BM-003, BM-004, BM-005, DV-007, MN-001, MN-009, JM-003, JM-006, JM-007, JM-008, JM-009, JM-011, JM-012, JM-013, WL-005 |
| **One row per person / case / incident** (register) | AG-001, AG-002, AG-003, AG-005, AN-002 to AN-007, AN-013, PR-008, PR-011, PR-013, PR-018, WL-002, WL-004, IT-001, IT-005, IT-008, BM-004/005 (per farmer) |
| **One row per budget head / scheme / work** | DV-001, DV-002, DV-003, DV-004, BD-001 (per arrear year), BD-002, BD-003, EX-005, LS-004, JM-001, JM-002, JM-005, CM-001, CM-002, WP-001, WP-002 (per working circle) |
| **One row per species / nursery / depot** | DV-006 (nursery × species), PD-007 (species), PD-008, PD-009, PD-010 (sale depot), EX-001 (nursery × species), EX-002 (species × source) |

## 3. Balance-sheet pattern (opening → received → disposed → closing)

About 30 formats are running balances keyed in by hand:

> गत माह तक / प्रा. शेष → माह में प्राप्त → कुल → माह में निराकृत / वसूल / परिवहित → शेष

Found in: PR-001, PR-003, PR-004, PR-005, PR-012, PR-014, PR-015, PR-016, PD-001, PD-002, PD-003, PD-004, PD-005, PD-006, PD-007, PD-008, PD-009, PD-010, BD-001, BD-002, BD-003, BD-004, EX-001, EX-002, EX-005, LS-004, LS-007, LS-008, VG-001, JM-001, JM-005, JM-010, JM-012, CM-001, CM-002, WP-001, WP-003.

The user types **both** the opening figure and the closing figure. The opening figure is not pulled from last month's closing figure, so the two can drift apart.

WL-001 and WL-003 are the exception: they are **cumulative to date** ("सभी इन्द्राज वर्तमान तक … पूर्व माह के संख्या/राशि को जोड़कर").

## 4. Units in use

| Quantity | Units seen |
|---|---|
| Money | **रु.** (BD, CM, LS-004, EX-005, PR, PD) vs **लाख** (DV-001, JM-*, BM-004/005) |
| Timber | घ.मी., नग (बल्ली/डेंगरी), जलाऊ **चट्टा** |
| Bamboo | नग, नो.टन, वि.ई.में. |
| Area | हे., कि.मी. (plantation), रकबा हे. |
| Work units (CAMPA) | किमी., हे., नग, मीटर, रन मीटर, बीट, श्रमिक, बेड, संख्या |
| Seed | कि.ग्रा. |

## 5. Masters the forms draw on

- **Employee Master**: AG-001/002/003/005, AN-003, IT-001 (name dropdown filled from designation)
- **Range list**: 4 territorial ranges; some forms add तमनार(उत्पादन), उर्दना (डिपो); AN-006 lists ranges of other divisions too
- **Species list**: one shared list (साल, सागौन, खमहार, नीलगिरी …) in DV-006, DV-007, PD-007, EX-001, EX-002
- **Nursery list**: DV-006 (Raigarh nurseries), EX-001 (state-wide list)
- **JFM samiti list**: JM-003, JM-007, JM-008, JM-011
- **Sale depot list**: PD-008/009/010 (state-wide)
- **Budget heads** (demand → major → minor → scheme): BD-002, BD-003, EX-005, LS-004, DV-003, DV-004, JM-001, JM-002

---

## 6. Format-by-format fields

### AG — प्रशासन (राजपत्रित)
| Code | Page | Row | Fields |
|---|---|---|---|
| AG-001 | AG/AG-001.aspx | Officer | पदनाम, नाम (Employee Master), पदस्थ कार्यालय, जन्म दि., पदस्थिति दि., पदस्थापना प्रकार (मूल/अतिरिक्त/रिक्त), कब से रिक्त, अतिरिक्त प्रभार, अद्यतन स्थिति, रिमार्क |
| AG-002 | AG/frmDEInfo.aspx | DE case | पदनाम, कार्यरत/सेवानिवृत्त, नाम, आरोप पत्र जारी/प्राप्ति तिथि, DE आरंभ आदेश व तिथि, जाँचकर्ता, प्रस्तुतकर्ता, अद्यतन स्थिति |
| AG-003 | AG/AN-006aspx.aspx | Pension case | नाम, Retirement/Death तिथि, अनुमानित पेंशन, स्वीकृति दि., लंबित कहाँ (वसं/वनमंडल/कोष), FBF, GIS, GPF, DPF, अवकाश नगदीकरण, उपादान, लंबित कारण |
| AG-005 | AG/AG-005.aspx | Show-cause notice | नाम, पदनाम, वर्तमान पदस्थापना, नोटिस जारी/प्राप्ति दि., प्रतिवाद उत्तर दि., अभिमत दि., स्थिति |

### AN — प्रशासन (अराजपत्रित)
| Code | Page | Row | Fields |
|---|---|---|---|
| AN-001 | AN/frmsetup.aspx | Post | प्रकार (नियमित/संख्येतर), पदनाम, कुल स्वीकृत; स्वीकृत/कार्यरत/रिक्त × (अ.जा., अ.ज.जा., पि.व., अनारक्षित) |
| AN-002 | AN/AN-007.aspx | DE case | आरोप पत्र क्र./दि., जवाब, DE आदेश/तिथि, जाँच अधिकारी, प्रतिवाद, DFO/CCF अभिमत, अभियोजन/बचाव साक्ष्य (पूर्ण/अपूर्ण), उपपत्ति, विलंब कारण |
| AN-003 | AN/AN-006aspx.aspx | Pension case | सेवानिवृति/मृत्यु तिथि, अमांग प्रमाण पत्र तिथि, कोष को प्रेषण, GPO/PPO, FBF…उपादान, लंबित कारण, निराकृत/लंबित |
| AN-004 | AN/AN-008.aspx | HC petition | याचिका क्र./वर्ष, याचिकाकर्ता, विषय, प्रभाग, प्रभारी अधिकारी, जवाबदावा (हाँ/नहीं, तिथि), आदेश तिथि/विवरण, अगली तिथि, पालन |
| AN-005 | AN/AN-009.aspx | District court case | same fields as AN-004 |
| AN-006 | AN/AN-001.aspx | Ranger | स्वीकृत संख्या; नाम, गृह जिला, जन्म, सेवानिवृति, पदस्थिति दि., स्तर (Circle/Division/Range), कार्यालय, प्रभार प्रकार |
| AN-007 | AN/AN-002.aspx | Dy.Ranger/Forester/Guard | पदस्थ संख्या; नाम, पदनाम, गृह जिला, जन्म, सेवानिवृति, स्थान, पदस्थिति दि. |
| AN-012 | AN/AN-011.aspx | Division total | 10% व 25% सीमा में रिक्त पद (सहा. ग्रेड-3, वनरक्षक, वाहन चालक, योग), चतुर्थ श्रेणी |
| AN-013 | AN/AN-012.aspx | Applicant | आवेदक, जन्म, दिवंगत सेवक, मृत्यु दि., संबंध, शिक्षा, पद, चतुर्थ श्रेणी सहमति, अनुसूचित क्षेत्र, श्रेणी, स्थिति (लंबित/निराकृत/नस्तीबद्ध) |

### WP — कार्य आयोजना
| Code | Page | Row | Fields |
|---|---|---|---|
| WP-001 | WP/WP01.aspx | Work type | कार्य प्रकार (ट्रेसिंग, Stock Mapping, सर्वेक्षण…), कुल कार्य, मासिक लक्ष्य, गत माह तक, माह में, शेष, % , कारण |
| WP-002 | WP/WP02.aspx | Working circle | Due कूप, कार्य/अकार्य/अपलेखित/अलाभकारी कूप, कारण (नक्सली/त्रुटिपूर्ण/अन्य), अनुमानित vs वास्तविक उत्पादन (CMT/नो.टन) |
| WP-003 | WP/WP003.aspx | Division | कुल मानचित्र, गत माह तक भेजे, माह में भेजे, Digitization उपरांत लौटे |

### DV — विकास / योजना
| Code | Page | Row | Fields |
|---|---|---|---|
| DV-001 | DV/frmDV012.aspx | Fin. year | प्रोजेक्ट संख्या/राशि, स्वीकृत/आबंटित/व्यय (लाख), पूर्ण/अपूर्ण/निरस्त, मानव दिवस, लाभान्वित |
| DV-002 | DV/frmDV013.aspx | Work | कार्य, संख्या, भौतिक लक्ष्य, स्वीकृत/प्राप्त राशि, माह में व्यय, पूर्ण/अपूर्ण |
| DV-003 | DV/frmDV017.aspx | Scheme × budget item | मुख्य मद (10/41/64), योजना, बजट मद, इकाई; लक्ष्य व उपलब्धि × (सामान्य, आ.उप.यो., वि.घ.यो.) |
| DV-004 | DV/frmDV018.aspx | Scheme | मांग → मद → योजना, आबंटन, व्यय |
| DV-006 | DV/frmDV014.aspx | Nursery × species | नर्सरी, बेड क्षमता, प्रजाति, संख्या |
| DV-007 | DV/frmDVNur.aspx | Site × species | योजना, परिक्षेत्र, स्थल/कक्ष, वन/गैर वन, रकबा (हे./किमी), प्रजाति, लक्ष्य, रोपित |

### PR — संरक्षण
| Code | Page | Row | Fields |
|---|---|---|---|
| PR-001 | PR/frmPR01.aspx | Division | विगत वर्ष तक/गत माह तक/माह में/कुल प्रकरण, अवैध काटे वृक्ष, अनुमानित उत्पादन व जप्त (काष्ठ घ.मी., बल्ली, चट्टा, मूल्य), हानि |
| PR-002 | PR/frmPR02.aspx | POR ≥ ₹50,000 | परिक्षेत्र, बीट, POR क्र./दि., वृक्ष, उत्पादन व जप्त (काष्ठ, चिरान, बल्ली, चट्टा, मूल्य), हानि, अपराधियों पर कार्यवाही, कर्मचारी व अनुशासनात्मक कार्यवाही |
| PR-003 | PR/frmPR03.aspx | Range | जाँच हेतु: प्रा.शेष, प्राप्त, जाँचे, न्यायालय में; अभिसंधान/अपलेखन हेतु: प्रा.शेष, प्राप्त, निराकृत, शेष |
| PR-004 | PR/frmPR04.aspx | Range | प्रारंभिक / माह में जप्त / डिपो परिवहित / शेष × (काष्ठ, बल्ली, चट्टा, अन्य) |
| PR-005 | PR/frmPR05.aspx | Range | मुआवजा व महसूल: माह पूर्व, निर्धारित, वसूल, शेष |
| PR-006 | PR/frmPR06.aspx | Range | प्रकरण, अपराधी, जप्त वनोपज (काष्ठ, बल्ली, चट्टा, अन्य, मूल्य), वाहन (प्रकार, पंजीयन, संख्या, मूल्य), न्यायालय/अभिसंधानित/लंबित |
| PR-007 | PR/frmPR061.aspx | Range | प्रकरण, अपराधी, मिट्टी/पत्थर/मुरुम/रेत/कोयला/अन्य (मात्रा, मूल्य), वाहन, कार्यवाही |
| PR-008 | PR/frmPR037.aspx | Case | POR, शिकार/तस्करी, तरीका (जहर/करेंट/हथियार), घटना, जप्त अवयव, अपराधी, गिरफ्तार, न्यायालय, पोस्टमार्टम, कर्मचारी संलिप्तता |
| PR-009 | PR/frmPR07.aspx | Division | रोस्टर निर्धारित/जाँची बीट × अधिकारी स्तर (DFO, SDO, RO, Dy.Ranger/Forester), नुकसान बीट, जप्त, हानि |
| PR-010 | PR/frmPR08.aspx | Division | आरामशीन पंजीकृत/चालू; निर्धारित/जाँची/परिणाम × (SDO, RO, परिक्षेत्र सहायक) |
| PR-011 | PR/frmPR09.aspx | Saw mill | नाम, स्थान, POR, जप्त घ.मी./मूल्य, मशीन, विद्युत विच्छेद, कार्यवाही (जप्त/राजसात/…), अनुज्ञप्ति आदेश, अपराध बार |
| PR-012 | PR/frmPR10.aspx | Range | वन क्षेत्रफल; अतिक्रमण गत माह/माह/कुल; बेदखली लंबित/की गई/शेष × (हे., प्रकरण, व्यक्ति) |
| PR-013 | PR/frmPR11.aspx | Case (WCCB) | detection date/place, item, quantity, agency, FIR/POR, sections, accused, court, status, species |
| PR-014 | PR/frmPR12.aspx | Division | लंबित/प्रस्तुत/निराकृत/शेष × (उच्च, अधीनस्थ न्यायालय) |
| PR-015 | PR/frmPR13.aspx | Division | जप्त वाहन गत माह/माह/योग; राजसात/निर्मुक्त/शेष (प्राधिकृत/अपीलीय/न्यायालय); निर्वर्तन लंबित/प्राप्त/किया/शेष |
| PR-016 | PR/frmPR14.aspx | Division | प्रा.शेष, माह में प्राप्त, मुख्यालय को प्रेषित, शेष |
| PR-017 | PR/frmPR15.aspx | Force | स्तर (वृत्त/वनमंडल/परिक्षेत्र), संख्या, POR, जप्त (काष्ठ, बल्ली, जलाऊ, अन्य, मूल्य), वाहन, गश्त/रात्रि गश्त/प्रवास दिवस |
| PR-018 | PR/frmPR47.aspx | Fire alert (from FMIS) | अग्नि ID, कक्ष, परिसर, सूचना तिथि; पाई गई (हाँ/नहीं), वन प्रकार, कारण, किसने बुझाई, प्रभावित रकबा, क्षति, उत्तरदायी |

### BM — बांस मिशन
| Code | Page | Row | Fields |
|---|---|---|---|
| BM-001 | BM/BM01.aspx | Centre × item | केन्द्र, समूह, सामग्री; निर्मित / एम्पोरियम विक्रय / स्थानीय विक्रय / शेष × (मात्रा, दर, राशि) |
| BM-003 | BM/BM04.aspx | Centre | परिक्षेत्र, केन्द्र, RO/प्रभारी/अध्यक्ष (नाम, मोबाइल), समिति व शिल्पी, प्रशिक्षण, चालू/बंद |
| BM-004 | BM/BM02.aspx | Farmer | परिक्षेत्र, हितग्राही, जाति, ग्राम, विकासखंड, रोपण वर्ष, रकबा, पौधे, प्रजाति, जीवित, अनुदान वर्ष 1/2 (लाख), जीवित % |
| BM-005 | BM/BM05.aspx | Farmer | as BM-004 + टिशु कल्चर vs साधारण पौधे |

### PD — उत्पादन
| Code | Page | Row | Fields |
|---|---|---|---|
| PD-001 | PD/PD01.aspx | Felling-area type | प्रकार (कार्य आयोजना/एरियर/FCA…), ड्यू वर्ष, कूप, रकबा, मार्क/विदोहित/शेष वृक्ष, उत्पादन/परिवहन/शेष × (इमारती घ.मी., बल्ली, डेंगरी, चट्टा) |
| PD-002 | PD/PD02.aspx | Range × area type | कूप, क्षेत्रफल, अनुमानित/विदोहित/परिवहित/शेष × (व्यापारिक, औद्योगिक बांस) |
| PD-003 | PD/PD03.aspx | Division | डिपो, वार्षिक लक्ष्य, उपलब्ध, प्रदाय, अवशेष × (निस्तार बांस, बल्ली, जलाऊ) |
| PD-004 | PD/PD04.aspx | Division | डिपो, पंजीकृत बसोड़, लक्ष्य, प्राप्त, प्रदाय, अवशेष |
| PD-005 | PD/PD05.aspx | Division | डिपो, माह पूर्व उपलब्ध, प्रदाय, अवशेष × (बांस, बल्ली, इमारती, जलाऊ) |
| PD-006 | PD/PD06.aspx | Division | गत माह शेष, माह में प्राप्त/स्वीकृत/भुगतान, शेष (प्रकरण, राशि) |
| PD-007 | PD/PD07.aspx | Species | पूर्व माह तक, माह में, कुल उत्पादन |
| PD-008 | PD/PD08.aspx | Sale depot | प्रस्तावित/विक्रय/Unsold काष्ठ, कीमत, राजस्व (पूर्व माह, माह में, माह अंत तक) |
| PD-009 | PD/PD09.aspx | Sale depot | as PD-008 for जलाऊ चट्टे |
| PD-010 | PD/PD10.aspx | Sale depot | प्रस्तावित/विक्रय/Unsold/कीमत/राजस्व × (व्यापारिक, औद्योगिक बांस, नो.टन) |
| PD-011 | PD/PD11.aspx | Source type | प्रकार (मालिक मकबूजा/POR/अन्य), वृक्ष, इमारती, बल्ली, डेंगरी, जलाऊ |

### LM — भू-प्रबंध (codes LS-)
| Code | Page | Row | Fields |
|---|---|---|---|
| LS-001 | LS/LS064.aspx | District | प्राप्त/स्वीकृत/अस्वीकृत-विचाराधीन दावे × (संख्या, रकबा) — व्यक्तिगत, प्रपत्र 3(क) |
| LS-002 | LS/LS065.aspx | District | same as LS-001 — सामुदायिक, प्रपत्र 3(ख) |
| LS-003 | LS/LS066.aspx | Unit × range | प्रारंभिक सर्वे क्षेत्र, उपयुक्त/सर्वेक्षित/शेष, अनुपयुक्त |
| LS-004 | BD/frmBD03.aspx?2 | Budget head | Form-7 व्यय: प्राप्त बजट, गत माह तक, चालू माह, कुल (रु.) |
| LS-005 | LS/LS002.aspx | Purpose | प्रयोजन, संख्या, रकबा — FRA 3(2) |
| LS-007 | LS/LS005.aspx | District × subject | विषय (नामांतरण/सीमांकन/बंटवारा/त्रुटिसुधार/अपील), लंबित/प्राप्त/निराकृत/अमान्य/%/शेष |
| LS-008 | LS/LS006.aspx | Division | जनमन सड़क स्वीकृत/लंबित/प्राप्त/स्वीकृत/शेष × (1980 पूर्व, FRA 3(2), योग) |

### BD — वित्त / बजट
| Code | Page | Row | Fields |
|---|---|---|---|
| BD-001 | BD/BD02.aspx | Arrear year (1981 →) | पिछला शेष, माह में देय, वसूल, अपलेखित, शेष (रु.) |
| BD-002 | BD/frmBD03.aspx?3 | Revenue head (0406) | वार्षिक लक्ष्य, गत माह तक, चालू माह, कुल प्राप्त (रु.) |
| BD-003 | BD/frmBD03.aspx?4 | Budget head | प्राप्त बजट, गत माह तक, चालू माह, कुल व्यय (रु.) |
| BD-004 | BD/frmBD01.aspx | Loss type (quarter) | पिछले त्रैमास लंबित, प्राप्त, कुल, निराकृत, शेष × (संख्या, राशि) |

### EX — अनुसंधान विस्तार
| Code | Page | Row | Fields |
|---|---|---|---|
| EX-001 | EX/EX103.aspx | Nursery × species | प्रारंभ में, तैयार, कुल, निर्वर्तित, शेष, पॉलिथिन/बेड में, किसको |
| EX-002 | EX/EX104.aspx | Species × source (SPA/SSO/CSO) | केन्द्र, प्रारंभिक, संग्रहित, कुल, निर्वर्तित, शेष (कि.ग्रा.), उपचारित |
| EX-003 | EX/EX105.aspx | Year | हितग्राही × (अ.जा., अ.ज.जा., सामान्य), रोपित, हस्तांतरित |
| EX-004 | EX/EX106.aspx | Plant type | साधारण/क्लोनल/ग्राफ्टेड/मिलिया डुबिया/TC बांस/TC सागौन: लक्ष्य, रोपित, हितग्राही |
| EX-005 | BD/frmBD03.aspx?5 | Budget head | Form-7: प्राप्त बजट, गत माह तक, चालू माह, कुल (रु.) |
| EX-006 | EX/EX108.aspx | Division | कुल हितग्राही, ऑनलाइन प्रविष्टि पूर्ण/अपूर्ण |

### MN — अनुश्रवण मूल्यांकन
| Code | Page | Row | Fields |
|---|---|---|---|
| MN-001 | MN/MN01.aspx?1 | Plantation inspected | अनुश्रवण वर्ष (प्रथम…अंतिम), रोपण वर्ष, योजना/मद, क्षेत्र संख्या, परिक्षेत्र, प्रकार (सिंचित/असिंचित/घेरा), स्थल, कार्यवृत, कूप, रोपित/जीवित |
| MN-002 | MN/MN02.aspx?1 | Plantation (non-forest) | as MN-001 + गांव, खसरा, क्षेत्रफल (किमी/हे.), प्रजातिवार पौधे |
| MN-005 | MN/MN007.aspx?0 | Allotted circle | वृत्त, निरीक्षणकर्ता वनमंडल, रोपण/मूल्यांकन वर्ष, कुल/DFO द्वारा/मुख्यालय मान्य मूल्यांकन |
| MN-008 | MN/MN02_M.aspx | Plantation year × type | कुल/चयनित क्षेत्र, क्षेत्रफल, रोपित, जीवित, जीवित %, निरीक्षणकर्ता |
| MN-009 | MN/MN008.aspx | Failed plantation | रोपण वर्ष, मद, परिक्षेत्र, स्थल, जीवित %, असफल घोषित पत्र, हानि राशि, वसूली आदेश, उत्तरदायी, वसूली योग्य/की गई |

### VG — सतर्कता शिकायत
| Code | Page | Row | Fields |
|---|---|---|---|
| VG-001 | VG/vg001.aspx?0 | Complaint source | स्रोत (मुख्यमंत्री निवास/सचिवालय/जनचौपाल/वनमंत्री/शासन…), गत माह शेष, प्राप्त, वनमंडल स्तर पर निराकृत, CCF को प्रेषित |
| VG-002 to VG-004 | — | — | Entry does not open for a division login (circle / HQ level forms) |

### JM — संयुक्त वन प्रबंधन
| Code | Page | Row | Fields |
|---|---|---|---|
| JM-001 | JM/JFM01.aspx | Scheme × work | वित्तीय वर्ष, योजना, कार्य, आबंटन, गत माह तक, माह में, कुल व्यय, % |
| JM-002 | JM/JFM02.aspx | Scheme × work | आबंटन/व्यय × (तैयारी PY-1, रोपण PY, रखरखाव PY+1…+4, अन्य), % |
| JM-003 | JM/JFM03.aspx | Range × samiti | मार्च 2023 शेष (समिति संख्या, बैंक मिलान), स्वीकृत कार्य, राशि (लाख), क्र./दि., व्यय, आहरित, शेष |
| JM-004 | JM/JFM04.aspx | Work | FDA में 2019 पूर्व राशि (बैंक स्टेटमेंट), CCF अनुमति, समितियाँ, राशि, क्र./दि. |
| JM-005 | JM/JFM05.aspx | Scheme × component | स्वीकृत/गत माह तक/माह में/कुल × (भौतिक, आर्थिक लाख) |
| JM-006 | JM/JFM06.aspx | Range | क्षेत्रफल, समितियाँ, आबंटित वन, सदस्य, बैठकें, वर्गीकरण (उत्कृष्ट/साधारण/कमजोर) |
| JM-007 | JM/JFM07.aspx | Range × samiti × work | स्वीकृत, माह में व्यय, शेष (लाख) |
| JM-008 | JM/JFMNew01.aspx | Range × samiti × activity | गतिविधि (ट्री गार्ड, वर्मी कम्पोस्ट, मशरूम…), स्वीकृति, कुल स्वीकृत, पूर्व माह/माह में/कुल व्यय (लाख) |
| JM-009 | JM/JFM08.aspx | Range | कुल समितियाँ, अंकेक्षण योग्य व पूर्ण (संख्या, लाख), मेजर ऑडिट कार्यवाही |
| JM-010 | JM/JFM009.aspx | Division | चक्रीय निधि: पूर्व/चालू/कुल जमा, पूर्व/चालू/कुल ऋण, वसूल, उपलब्ध (लाख) |
| JM-011 | JM/JFM010.aspx | Range × samiti × work | ऋण राशि, स्वीकृति क्र./तिथि, भौतिक/आर्थिक प्रगति, वसूली गत माह/माह/कुल |
| JM-012 | JM/JFMNEW07.aspx | Range | ग्राम सभाएँ, CFRR गत माह तक/माह में/कुल × (संख्या, हे.) |
| JM-013 | JM/JFMNEW05.aspx | Range | व्यक्तिगत वन अधिकार (संख्या, क्षेत्रफल), FRA क्लस्टर, स्वीकृत/किया गया कार्य, रकबा, राशि |
| JM-014 | JM/JFMNEW06.aspx | Office | चराई केन्द्र, गोबर क्रय (क्विंटल, लाख), भुगतान, वर्मी/सुपर कम्पोस्ट (मात्रा, राशि) |
| JM-015 | JM/JFMGIM.aspx | Work | GIM 2019 पूर्व राशि (बैंक स्टेटमेंट), CCF अनुमति, समितियाँ, राशि, क्र./दि. |

### IT — मा.सं.वि. / सू.प्रौ.
| Code | Page | Row | Fields |
|---|---|---|---|
| IT-001 | IT/hrd02.aspx | Officer × training | पदनाम, नाम, संस्थान, प्रारंभ/समापन, विषय, राज्य बाहर अनुमति, उपस्थिति, प्रमाण पत्र (PDF upload) |
| IT-002 to IT-004 | — | — | Entry does not open for a division login (forest school / circle level) |
| IT-005 | IT/hrd05.aspx | Trainee | विषय, संस्थान, नाम, पदनाम, कार्यालय, मोबाइल, ईमेल |
| IT-008 | IT/IT04.aspx | Staff × task | नाम, पदनाम (Programmer/DEO/GIS…), कार्य प्रकृति, विवरण, संख्या, घंटे, प्रोजेक्ट — "Only RGCs are allowed for entry" |

### CM — CAMPA
| Code | Page | Row | Fields |
|---|---|---|---|
| CM-001 | CM/Campa02.aspx?0 | मद × कार्य (APO 2026-27) | मद (अनिवार्य/Interest 60%/40%/NPV 20%/80%), कार्य (20 types: CA, PCA, CAT, IWMP, transmission line, SMC…), APO प्रावधानित व स्वीकृत × (भौतिक, इकाई, आर्थिक रु.), गत माह तक व्यय, चालू माह व्यय, कुल, % |
| CM-002 | CM/Campa02.aspx?1 | same, APO 2025-26 | same fields |

### WL — वन्यप्राणी
| Code | Page | Row | Fields |
|---|---|---|---|
| WL-001 | WL/wl1.aspx | Loss type (cumulative) | जनहानि/जनघायल/अपंग/पशु/फसल/मकान/अन्य × (पंजीकृत, निराकृत, भुगतान रु., लंबित, फसल रकबा) |
| WL-002 | WL/wl2.aspx | Death incident | स्थल, संख्या, लिंग, आयु, दिनांक, कारण |
| WL-003 | WL/wl3.aspx | Loss type (cumulative) | as WL-001 for बाघ/तेंदुआ/भालू/अन्य |
| WL-004 | WL/wl4.aspx | Case | detection date/place (District/Range/Beat), agency, FIR/POR, natural/unnatural, cause, species, item, sections, accused |
| WL-005 | WL/wl5.aspx | Death incident | परिक्षेत्र, स्थल (बीट/कक्ष), घटना दि., सूचना क्र./दि., वन्यप्राणी, संख्या, कारण |

---

## 7. Problems seen (inputs for the redesign)

1. **Openings typed by hand.** "गत माह तक" is re-typed every month instead of being carried from last month's closing → totals drift. *Same as Last Month* copies the whole row, so stale closings get re-sent.
2. **Same data asked twice.** AG-003 and AN-003 use one page; AN-004/005 vs PR-014 (court cases); PR-016 vs VG-001 (complaints); BD-003 / EX-005 / LS-004 are one Form-7 page with different heads; DV-006 vs EX-001 (nursery stock).
3. **Money units mixed.** रु. in BD/CM/PR, लाख in DV/JM/BM: a cross-format total needs conversion.
4. **Cumulative vs monthly not uniform.** WL-001/003 are cumulative-to-date, everything else is monthly + manual running total.
5. **State-wide masters shown to a division.** AN-006 range list, EX-001 nurseries, PD-008/009/010 depots list other divisions; SUKMA, CHIRWANI appear twice.
6. **Stale labels.** DV-007 heading says 2025 (title 2026); WL-004 "Year 2023"; JM-003/004 fixed to March 2023 / 2022; WP-002 heading says मासिक on an annual form; EX-002 heading says त्रैमासिक on a monthly form; "Frebuary" in month list; "आवयकता नही है".
7. **Forms not enterable at division level** still sit in the division's list (VG-002/003/004, IT-002/003/004, IT-008 RGC-only), which inflates "pending" counts.
8. **Free-text where a code exists.** POR number, स्थल/कक्ष, scheme names in MN-001 (योजना का नाम, योजना मद) are free text, so they can't be joined to other formats.
