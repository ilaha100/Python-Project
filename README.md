# Oyuncu Analizi Layihəsi

Bu layihə futbol oyuncularının müxtəlif xüsusiyyətlərini analiz etmək üçün hazırlanmışdır. Burada datasetin yüklənməsi və ilkin analizi, məlumatların təmizlənməsi (preprocessing) və vizualizasiya mərhələləri əhatə olunur. Layihədə əsas məqsəd oyuncuların performanslarını və digər amillər arasındakı əlaqələri daha yaxşı başa düşməkdir.

## İstifadə Olunan Alətlər və Kitabxanalar
Bu layihədə aşağıdakı Python kitabxanalarından istifadə olunmuşdur:
- **NumPy**: Verilənlərin analizi və riyazi əməliyyatlar.
- **Pandas**: Verilənlərin yüklənməsi, işlənməsi və analiz edilməsi.
- **Matplotlib**: Məlumatların vizual təqdimatı üçün.
- **Seaborn**: İstifadə edilən qrafiklərin daha cəlbedici və interaktiv olması üçün.

## 1. Datasetin Yüklənməsi və Kəşf Edilməsi
- **Datasetin yüklənməsi**: Verilənlər CSV faylı kimi yüklənib `pandas` kitabxanası vasitəsilə oxunmuşdur.
- **İlkin baxış**: Datasetin ilk 20 dayağı göstərilmiş və sütunlarda mövcud olan `Unnamed` sütunlar silinmişdir.
- **Sütunların göstərilməsi**: Sütunların tam şəkildə görsənməsi üçün `pd.set_option()` funksiyasından istifadə olunmuşdur.
- **Sütun məlumatlarının xülasəsi**: Datasetdə beş rəqəmdən ibarət sütunların statistik xülasəsi `describe()` funksiyası vasitəsilə əldə edilmişdir.

## 2. Preprocessing (Məlumatların Təmizlənməsi)
- **Qiymət sütununun təmizlənməsi**: `Value` sütunundakı Euro işarəsi və `M`, `K` hərfləri müvafiq olaraq 1000000 və 1000 ilə əvəzlənmişdir.
- **Məlumatların rəqəmə çevrilməsi**: Ədədi formatlara çevrilmə üçün `astype()` funksiyasından istifadə olunmuşdur.
- **Null dəyərlərin əvəz edilməsi**: Datasetdəki boş (null) dəyərlər `fillna()` metodu ilə 0 ilə əvəz olunmuşdur.

## 3. Visualization and Analysis
Layihədə oyuncuların müxtəlif xüsusiyyətləri və onlara aid vizual təhlillər aparılmışdır:

### 3.1 Oyuncuların Pozisiya Paylanması
- **Bar chart**: Oyuncuların `Position` sütununa əsasən paylanması `value_counts()` və `plot()` funksiyaları ilə bar chart kimi göstərilmişdir.

### 3.2 Oyuncuların Yaş Paylanması
- **Histogram**: Oyuncuların yaşlarının paylanması `plot(kind='hist')` vasitəsilə təqdim edilmişdir.
- **KDE Plot**: Yaş paylanmasının göstərilməsi üçün `kdeplot()` istifadə edilmişdir.

### 3.3 Oyuncuların İstifadə Etdiyi Ayağın Qiymətə Təsiri
- **Countplot və Pie chart**: Oyuncuların hansı ayağını (sol və ya sağ) istifadə etdiyinə görə paylanma göstərilmişdir.
- **Ortalama qiymətin tapılması**: `groupby()` funksiyası ilə ayağa görə ortalama qiymət hesablanmış və `bar chart` ilə göstərilmişdir.

### 3.4 İstifadə Olunan Ayağın və Pozisiyanın Qiymətə Təsiri
- **Countplot**: `Position` və `Preferred Foot` sütunlarına görə oyuncuların sayı göstərilmişdir.
- **Y oxisinin təyin edilməsi**: Qiymət faktorunun y oxisi olaraq əlavə edilməsi ilə vizual analiz aparılmışdır.

### 3.5 Beynəlxalq Reputasiya və Oyuncu Potensialı Arasındakı Əlaqə
- **Distinct dəyərlərin göstərilməsi**: `unique()` funksiyası ilə beynəlxalq reputasiyanın fərqli dəyərləri göstərilmişdir.
- **Swarm plot**: Beynəlxalq reputasiya və potensial arasındakı əlaqəni göstərmək üçün `swarmplot()` istifadə edilmişdir.

## Nəticələr və Əlavə Məlumatlar
Bu layihə nəticəsində oyuncuların fərqli xüsusiyyətləri və bunların dəyərə təsiri haqqında ətraflı təhlillər aparılmışdır. Bu, komandaların transfer siyasətində və oyunçu analizlərində əhəmiyyətli məlumatlar verə bilər. Daha detallı təhlillər üçün `Seaborn` və `Matplotlib` kitabxanalarının digər vizualizasiya metodlarından da istifadə oluna bilər.

## Beynəlxalq Reputasiya və Oyuncu Potensialı - İstifadə olunan ayaq arasındakı əlaqə
- **Strip plot**: Beynəlxalq reputasiya və oyuncu potensialı ilə istifadə olunan ayaq arasındakı əlaqəni göstərmək üçün `stripplot()` istifadə olunmuşdur. `hue` parametri ilə fərqli ayaqları göstərən rəngli göstərici əlavə edilmişdir.
- **Boxplot**: Bu əlaqəni daha aydın göstərmək üçün `boxplot()` funksiyası ilə qrafik qurulmuşdur.

## Oyuncuların Potensialları və Gücləri arasındakı əlaqə
- **Lineplot**: Oyuncuların potensial və gücləri arasındakı əlaqəni göstərmək üçün `lineplot()` funksiyasından istifadə edilmişdir.

## Oyuncuların Potensialları və Gücləri - İstifadə olunan ayaq arasında
- Bu analizdə potensial, güc və istifadə olunan ayaq arasındakı əlaqəni təhlil etmək üçün uyğun qrafik növləri istifadə olunmuşdur.

## Dashboard
- **Dashboard**: Layihənin sonunda bir 15x15 ölçülü fiqur yaradılmış və dörd subplot yerləşdirilərək yuxarıda qurulmuş qrafiklər bir dashboard-a inteqrasiya edilmişdir.


Layihənin tam kodları və əlavə izahlar README-də təqdim olunmuşdur. Kod nümunələrini icra etmək üçün `Python 3.x` və yuxarıda göstərilən kitabxanaların quraşdırılması tələb olunur.
