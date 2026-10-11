# Teach_HID_Doppler_KKN_summerStorm

**สอนวิเคราะห์ข้อมูลเรดาร์ Doppler และ dual-polarization ด้วย Python/Colab ผ่านเคสพายุฤดูร้อน 3 พฤษภาคม 2567 (เรดาร์ขอนแก่น KKN, กรมอุตุนิยมวิทยา)**

ชุด notebook 6 บท สำหรับนิสิตปริญญาตรีปี 3–4 และปริญญาโทด้านวิทยาศาสตร์สิ่งแวดล้อม ภูมิศาสตร์ และอุตุนิยมวิทยา
เนื้อหาครอบคลุมการแก้การพับของความเร็ว Doppler, ลายเซ็นของ downburst, ความปั่นป่วนจาก spectrum width (PyTDA),
การประมวลผล ΦDP/KDP/ZDR และการลดทอนสัญญาณ, การจำแนกชนิดหยาดน้ำฟ้าแบบ fuzzy (HID) และการสังเคราะห์ตัวชี้วัดทั้งวัน
ทุก notebook เป็นภาษาไทย มีวัตถุประสงค์ สมการสำคัญ แผนที่คุณภาพตีพิมพ์ แบบฝึกหัด 3 ข้อพร้อมเฉลยโค้ด คำถามชวนคิด และแนวทางต่อยอดงานวิจัย

> Repo คู่กัน: [Teach_Pysteps_KKN_summerStorm](https://github.com/nattaponm/Teach_Pysteps_KKN_summerStorm) — nowcasting ด้วย pysteps จาก pseudo-CAPPI 2 km ของพายุลูกเดียวกัน

## 📚 Notebooks

| # | Notebook | เนื้อหาหลัก | Colab |
|---|---|---|---|
| 1 | [01_polar_radar_variables](notebooks/01_polar_radar_variables.ipynb) | โครงสร้างข้อมูล polar, ตัวแปร 6 ชนิด, Doppler dilemma, ความสูงลำคลื่นเทียบระดับ 0 °C, ตรวจคุณภาพ (qc_flag, ZDR bias, ρHV, ΦDP) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/01_polar_radar_variables.ipynb) |
| 2 | [02_doppler_dealiasing_outflow](notebooks/02_doppler_dealiasing_outflow.ipynb) | Dealiasing 3 วิธี (region-based, unwrap phase, sounding first guess/4DD), ผลของพารามิเตอร์, divergence และ azimuthal shear, ลายเซ็น downburst ที่ภูกระดึงและนากลาง | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/02_doppler_dealiasing_outflow.ipynb) |
| 3 | [03_spectrum_width_turbulence_pytda](notebooks/03_spectrum_width_turbulence_pytda.ipynb) | ที่มาของ spectrum width, EDR และทฤษฎี Kolmogorov, PyTDA (NTDA), EDR ตามพื้นที่–เวลา–ความสูง | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/03_spectrum_width_turbulence_pytda.ipynb) |
| 4 | [04_dualpol_kdp_zdr_attenuation](notebooks/04_dualpol_kdp_zdr_attenuation.ipynb) | ประมวลผล ΦDP ทีละขั้น (กลับเครื่องหมาย, unwrap, system phase), KDP, ZDR bias, Z-PHI attenuation | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/04_dualpol_kdp_zdr_attenuation.ipynb) |
| 5 | [05_hydrometeor_classification_fuzzy](notebooks/05_hydrometeor_classification_fuzzy.ipynb) | Fuzzy logic และ semi-supervised HID (Besic et al. 2016), พัฒนาการของคลาส, ภาคตัดขวางผ่านนากลาง, ความไวต่อ ZDR/ระดับเยือกแข็ง | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/05_hydrometeor_classification_fuzzy.ipynb) |
| 6 | [06_storm_evolution_synthesis](notebooks/06_storm_evolution_synthesis.ipynb) | ตัวชี้วัดทั้งวัน 92 volume, แผนที่ swath (ลูกเห็บ, ความเร็ว, divergence, EDR), แฟ้มพายุรายพื้นที่, ส่งออก GeoTIFF/GeoPackage, correlation และ lag | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nattaponm/Teach_HID_Doppler_KKN_summerStorm/blob/main/notebooks/06_storm_evolution_synthesis.ipynb) |

`notebooks/00_prepare_polar_for_doppler_pytda_hid.ipynb` คือ notebook เตรียมข้อมูลจากไฟล์ UF ดิบ (สำหรับผู้สอน/ผู้ที่มีข้อมูลต้นฉบับ)

**ลำดับการเรียนที่แนะนำ:** 1 → 2 → 3 (Doppler) และ 1 → 4 → 5 (dual-pol) แล้วจบที่ 6
แต่ละ notebook ใช้เวลา 60–90 นาที และรันจบใน Colab ได้ภายใน 2–5 นาที (NB6 ใช้ข้อมูลที่คำนวณล่วงหน้า)

## 🗂️ โครงสร้าง repo

```
data/
├── polar_all/            92 volume (00:00–23:45 UTC, ขาด 04:00–04:45) CfRadial ขนาดเล็ก ~0.2–0.7 MB/ไฟล์
├── KKN_20240503/         inventory, volume_stats, manifest และ 8 volume ช่วงพีค (09:00–10:45 UTC)
├── derived/              ตัวชี้วัดทั้งวันที่คำนวณล่วงหน้า (ใช้ใน NB6)
│   ├── KKN_20240503_volume_metrics.csv
│   └── KKN_20240503_swaths.nc
├── sounding/             sounding 48431 (นครราชสีมา) 00Z 3 พ.ค. 2567
├── reports/              จุดรายงานความเสียหาย 19 จุด (ระดับตำบล) + README แหล่งข่าว
└── basemap/              ขอบเขตประเทศ/จังหวัด/อำเภอ และภูมิประเทศ (สำหรับแผนที่)
utils/
├── polar_tools.py        ฟังก์ชันหลักของ repo นี้ (dealiasing, divergence, ΦDP/KDP, Z-PHI, HID, PyTDA, gridding, swath)
├── mapplot.py            แผนที่ AEQD คุณภาพตีพิมพ์ (ใช้ร่วมกับ repo pysteps)
├── kkn_tools.py          จุดรายงาน พิกัด และเครื่องมือเสริมของเคส
├── sounding_tools.py     อ่าน/วิเคราะห์ sounding
└── data_io.py            บันทึก GeoTIFF
notebooks/                01–06 (+ 00 เตรียมข้อมูล)
figures/                  รูปจาก notebook เตรียมข้อมูล
```

### ข้อมูล polar (gentle QC)
ทุกไฟล์มี `reflectivity_raw`, `reflectivity_qc`, `velocity_qc` (**ยังพับอยู่**, Vny = 8.38 m/s ช่วงพายุ), `spectrum_width_qc`,
`differential_reflectivity_qc`, `differential_phase_qc`, `cross_correlation_ratio_qc` และ `qc_flag` (bit: 1 ไม่มี echo, 2 flare ray,
4 non-met, 8 speckle, 16 σv ใช้ไม่ได้, 32 V ใช้ไม่ได้, 64 ΦDP texture สูง) — 4 มุมยก (0.48°, 1.48°, 2.39°, 3.39°) × 480 gate × 500 m

### ค่าที่ใช้ใน `polar_tools.py` (ปรับได้)
| ขั้นตอน | ค่าตั้งต้น | หมายเหตุ |
|---|---|---|
| Region-based dealiasing | `skip_between_rays = skip_along_ray = 0`, `centered=False` | ค่าตั้งต้นของ Py-ART เลื่อนเซลล์ที่แยกขาดผิดทั้งก้อนในเคสนี้ (ดู NB2) |
| Sounding first guess | 2 pass, หน้าต่าง 5 ray × 21 gate | หลักการขั้นแรกของ 4DD (Py-ART 2.x ยกเลิก `dealias_fourdd`) |
| ΦDP | ตรวจเครื่องหมายอัตโนมัติ, ρHV > 0.85, Z > 10 dBZ, texture < 20°, median 11 gate + isotonic regression | KKN: ΦDP ลดลงตามระยะในทุก sweep ของข้อมูลชุดนี้ |
| KDP | Vulpiani et al. (2012), windsize 10 gate | |
| ZDR | บวก +0.20 / +0.39 / +0.39 / +0.39 dB (ราย sweep) | ตรวจด้วยฝนเบาใน NB1 |
| Z-PHI | a = 0.073, b = 0.64884 | Testud et al. (2000) |
| HID | `hydroclass_semisupervised`, 5.6 GHz, weights (1, 1, 1, 0.75, 0.5) | ลูกเห็บใน NB6 = MH/IH/HDG และ Z ≥ 40 dBZ |
| PyTDA | radius 2 km, `split_cut=False`, beamwidth 1°, gate 0.5 km | |

## ▶️ การใช้งาน

**Google Colab (แนะนำ):** กดปุ่ม *Open in Colab* แล้วรันเซลล์ ⚙️ Setup ก่อน (ติดตั้งแพ็กเกจและ clone repo อัตโนมัติ ~2–3 นาที)

**เครื่องตัวเอง:**
```bash
git clone https://github.com/nattaponm/Teach_HID_Doppler_KKN_summerStorm.git
cd Teach_HID_Doppler_KKN_summerStorm
pip install -r requirements.txt
pip install --no-build-isolation git+https://github.com/nasa/PyTDA.git    # สำหรับ NB3 และ NB6
jupyter lab
```

**คำนวณตัวชี้วัดทั้งวันใหม่** (เช่น หลังปรับพารามิเตอร์): ตั้ง `RUN_FULL = True` ใน NB6 หรือ
```python
from utils import polar_tools as pt
pt.run_whole_day("data", "output/derived_rerun", sites={...})
```

## 🙏 แหล่งข้อมูลและการอ้างอิง
- ข้อมูลเรดาร์: **กรมอุตุนิยมวิทยา (TMD)** — ใช้เพื่อการศึกษา
- Sounding: University of Wyoming (สถานี 48431)
- ขอบเขตการปกครอง: geoBoundaries (CC BY 4.0); ภูมิประเทศ: AWS Terrain Tiles (SRTM/GMTED2010)
- รายงานความเสียหาย: ปภ. และสื่อมวลชน (ดู `data/reports/README.md`)
- ซอฟต์แวร์: [Py-ART](https://arm-doe.github.io/pyart/) (Helmus & Collis, 2016), [PyTDA](https://github.com/nasa/PyTDA), cartopy, geopandas

ถ้านำไปใช้ในงานวิจัย กรุณาอ้างอิง repo นี้ และ Py-ART: Helmus, J. J., & Collis, S. M. (2016). *J. Open Research Software*, 4, e25.
