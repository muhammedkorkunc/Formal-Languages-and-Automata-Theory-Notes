cat << 'EOF' > README.md

# ⚙️ Formal Languages & Automata Theory Lecture Compendium

### Biçimsel Diller, Otomata Teorisi, Düzenli İfadeler (Regex) ve Gramer Analizleri

Bu depo; Bilgisayar Mühendisliği lisans programı kapsamında **Biçimsel Diller ve Otomata Teorisi (Formal Languages & Automata Theory)** dersi süresince tutulan 56 sayfalık kapsamlı el yazması çalışma defterini barındırır. Sonlu durum makineleri, dillerin hesaplanabilirlik sınırları ve dilbilgisi ayrıştırma ağaçları detaylıca incelenmiştir.

---

## 📑 İncelenen Konseptler ve Teorik Modüller

| Modül  | Konu Başlığı                              | Kapsanan Temel Algoritmalar ve Teoremler                                                                                                                                              |
| :----- | :---------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **01** | **Temel Terminoloji**                     | Alfabeler ($\Sigma$), Alfabe kuvvetleri ($\Sigma^k, \Sigma^*$), Stringler, Boş Karakter ($\epsilon$), Birleştirme (Concatenation) ve Karar Problemleri (Decision Problems).           |
| **02** | **Deterministik Sonlu Otomatlar (DFA)**   | 5-Tüp tanımı $M = (Q, \Sigma, \delta, q_0, F)$, geçiş fonksiyonları ($\delta$), durum tabloları, Dead/Trap State mekanizmaları ve Minimal DFA tasarımı.                               |
| **03** | **Deterministik Olmayan Otomatlar (NFA)** | Durum dallanmaları, kilitlenme (stuck) senaryoları, $\epsilon$-geçişleri ($\epsilon$-NFA) ve $\epsilon$-Closure (kapanış) kümeleri.                                                   |
| **04** | **NFA $\to$ DFA Eşdeğerliği**             | Alt Küme İnşası (**Subset Construction Algorithm**) ile $2^{\vert{}Q\vert{}}$ üstel durum uzayından erişilebilir durumların (Lazy Evaluation) tespiti.                                |
| **05** | **Düzenli İfadeler (Regex)**              | Birleşim ($+$), ardıştırma, Kleene Star ($*$), durum eleme (**State Elimination Method**) ile otomatlardan regex üretimi.                                                             |
| **06** | **Pumping Lemma (Pompalama Teoremi)**     | Pigeonhole (Güvercin Yuvası) Prensibi ile bir dilin düzenli (regular) olmadığını çelişki ($w = xyz, \vert{}xy\vert{} \le p, \vert{}y\vert{} > 0, xy^i z \notin L$) yoluyla ispatlama. |
| **07** | **Bağlamdan Bağımsız Diller (CFG)**       | Gramer 4-tüpü $G = (V, T, P, S)$, Leftmost/Rightmost türetimler, Ayrıştırma Ağaçları (Parse Trees) ve Belirsizlik (Ambiguity) analizi.                                                |

---

## 📐 Önemli Teoremler ve Matematiksel Modeller

### 1. Deterministik Sonlu Otomatın (DFA) Biçimsel Tanımı

DFA bir 5-tüp olarak formüle edilir:

$$M = (Q, \Sigma, \delta, q_0, F)$$

- $Q$: Sonlu durumlar kümesi
- $\Sigma$: Giriş alfabesi
- $\delta: Q \times \Sigma \to Q$: Durum geçiş fonksiyonu
- $q_0 \in Q$: Başlangıç durumu
- $F \subseteq Q$: Kabul (final) durumları kümesi

---

### 2. Düzenli Diller İçin Pumping Lemma

Eğer $L$ düzenli bir dil ise, öyle bir $p \ge 1$ pompalama uzunluğu vardır ki; $\vert{}w\vert{} \ge p$ koşulunu sağlayan her $w \in L$ kelimesi şu şartları sağlayacak şekilde $w = xyz$ olarak üçe ayrılabilir:

1. $\vert{}xy\vert{} \le p$
2. $\vert{}y\vert{} > 0$
3. $\forall i \ge 0 \implies x y^i z \in L$

Bu şartlardan birinin $i$ değeri için bozulması (örneğin $L = \{0^n 1^n \mid n \ge 1\}$ veya $L = \{ww \mid w \in \{a,b\}^*\}$), dilin düzenli olmadığını kanıtlar.

---

### 3. Bağlamdan Bağımsız Gramer (CFG)

Bir CFG grameri şu bileşenlerle tanımlanır:

$$G = (V, T, P, S)$$

Burada $V$ değişkenleri (non-terminals), $T$ uç simgeleri (terminals), $P$ üretim kurallarını ($A \to \alpha$) ve $S \in V$ başlangıç simgesini ifade eder.

---

## 🔒 Copyright & License / Telif Hakkı Bildirimi

Bu arşiv ve beraberindeki el yazması ders dokümanları **Proprietary (Tescilli / Tüm Hakları Saklıdır)** lisansına tabidir.

```text
Copyright (c) 2026 Muhammed Emin Korkunç. All Rights Reserved.

Bu belgede yer alan tüm el çizimi otomat şemaları, durum tabloları,
Pumping Lemma ispatları, CFG türetimleri ve ders notları Muhammed Emin Korkunç'a aittir.
Yazarın açık yazılı izni olmaksızın kısmen veya tamamen kopyalanması,
dağıtılması veya akademik/ticari amaçla izinsiz kullanımı kesinlikle yasaktır.

👨‍💻 Geliştirici / Author
Muhammed Emin Korkunç

GitHub: @muhammedkorkunc

LinkedIn: Muhammed Emin Korkunç

Email: muhammedemin.korkunc@gmail.com
```
