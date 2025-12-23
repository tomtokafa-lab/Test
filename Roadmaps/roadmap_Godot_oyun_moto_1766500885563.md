Eğitmen gözüyle yaptığım incelemede tespit ettiğim **kabul edilemez** hatalar şunlardır:

1.  **Dizi (Array) Bilgisi Olmadan Grup Yineleme (Hafta 3):** 3. Hafta 3. Gün'de "Node Grupları" anlatıp, 4. Gün'de "Diziler (Arrays)" anlatmışsın. Godot'da `get_tree().get_nodes_in_group()` fonksiyonu bir **Array** döndürür. Öğrenci daha dizinin ne olduğunu, indeks mantığını bilmeden, dönen veriyi `for` döngüsüne sokamaz. Bu pedagojik bir intihardır. Önce Dizi, sonra Grup gelmeli.
2.  **Tween Yapısının Yokluğu:** Godot'nun en güçlü ve modern silahı olan `CreateTween()` roadmap'te yok. "Cilalama" (Juice) haftasında veya UI haftasında Tween olmadan animasyon yapmak, öğrenciyi gereksiz yere `_process` içinde matematik boğuşmasına iter. Bu modern Godot 4.x akışında **zorunludur**.

Aşağıda bu hataların giderildiği, mantıksal akışın düzeltildiği **NİHAİ ROADMAP** yer almaktadır:

---

# DÜZELTİLMİŞ GODOT & GDSCRIPT ROADMAP (FİNAL VERSİYON)

Bu plan, Array/Grup sıralamasını düzeltmiş ve modern Godot geliştiriciliğinin temeli olan Tween yapısını entegre etmiştir.

---

## 1. Hafta: Temeller, Fonksiyonlar ve Vektörler
**Odak:** Kodlama Mantığına Giriş ve Uzay Algısı

*   **Gün 1: Godot Arayüzü, Node2D ve İlk Script**
    *   Görev: Sahne oluşturma, Node2D ekleme, script bağlama. `print("Merhaba")` çıktısı.
*   **Gün 2: Değişkenler ve Veri Tipleri**
    *   Görev: `var`, `const`, `int`, `float`, `String`, `bool`.
*   **Gün 3: Fonksiyonların Mantığı**
    *   Görev: `func` tanımlama, parametre gönderme (Girdi -> İşlem -> Çıktı).
*   **Gün 4: Vektör Matematiği (Vector2)**
    *   Görev: `Vector2(x, y)` nedir? Pozisyon manipülasyonu.
*   **Gün 5: Operatörler ve Basit Hesaplamalar**
    *   Görev: Toplama, çıkarma ve vektör işlemleri.
*   **Gün 6: Tip Belirleme (Static Typing)**
    *   Görev: `var hiz: float = 100.0` sözdizimine alışkanlık kazanma.
*   **Gün 7: Uygulama - Hareket Eden İkon**
    *   Görev: Kod ile ikonu her çalıştırışta ekranın rastgele bir yerine koyan script.

---

## 2. Hafta: Kontrol Akışı ve Temel Hareket
**Odak:** Karar Mekanizmaları ve Oyun Döngüsü

*   **Gün 1: If / Elif / Else Koşulları**
    *   Görev: Mantıksal operatörler (`>`, `<`, `==`).
*   **Gün 2: Oyun Döngüsü ve Delta Zamanı (`_process`)**
    *   Görev: `delta` ile kare hızı bağımsız hareket mantığı.
*   **Gün 3: Basit Hareket (Input Olmadan)**
    *   Görev: `position.x += speed * delta`.
*   **Gün 4: Input Map ve Girdi Okuma**
    *   Görev: Proje ayarlarından tuş atama ve `Input.is_action_pressed`.
*   **Gün 5: Match (Switch) Yapısı**
    *   Görev: Durum kontrolü (State management basics).
*   **Gün 6: Karakter Sınırlama (Clamp)**
    *   Görev: Karakteri ekran sınırları içinde tutma.
*   **Gün 7: Uygulama - Basit Uzay Gemisi**
    *   Görev: 4 yöne hareket eden, ekrandan çıkamayan gemi.

---

## 3. Hafta: Veri Yapıları ve Sahne Ağacı (DÜZELTİLDİ)
**Odak:** Veriyi Yönetmek ve Hiyerarşi (Sıralama Hatası Giderildi)

*   **Gün 1: Sahne Ağacı (Scene Tree) Mantığı**
    *   Görev: Parent-Child ilişkisi. `get_node()`, `$Node` kullanımı.
*   **Gün 2: Döngüler (For ve While)**
    *   Görev: `for i in range()` ve tekrarlayan işlemler.
*   **Gün 3: Diziler (Arrays)**
    *   **Düzeltme:** Önce liste mantığı öğrenilmeli. Ekleme (`append`), okuma.
*   **Gün 4: Node Grupları ve Toplu İşlem**
    *   **Düzeltme:** Array öğrenildiğine göre şimdi Grup'tan dönen Array'i döngüye sokabiliriz. Tüm düşmanları tek seferde yok etme.
*   **Gün 5: Sözlükler (Dictionaries)**
    *   Görev: Anahtar-Değer ilişkisi (Envanter verisi vb.).
*   **Gün 6: Sahne Örnekleme (Instantiating)**
    *   Görev: `preload` ve `instantiate` ile koddan obje yaratma.
*   **Gün 7: Uygulama - Mermi Sistemi**
    *   Görev: Tuşa basınca karakterden mermi (Scene) çıkaran sistem.

---

## 4. Hafta: Sinyaller ve Çarpışma
**Odak:** Olay Tabanlı Programlama

*   **Gün 1: Area2D ve Çarpışma Mantığı**
    *   Görev: `area_entered`, `body_entered` sinyalleri.
*   **Gün 2: Sinyaller (Signals) - Editör**
    *   Görev: Butona tıklama vb. olayları editörden bağlama.
*   **Gün 3: Özel Sinyaller (Custom Signals)**
    *   Görev: `signal` tanımlama ve `emit()` ile yayınlama.
*   **Gün 4: Kod ile Sinyal Bağlama**
    *   Görev: `.connect()` metodu ile dinamik bağlantı.
*   **Gün 5: Timer Node'u**
    *   Görev: Zamanlayıcılar ve Cooldown mantığı.
*   **Gün 6: Rastgelelik (Randomization)**
    *   Görev: `randf()`, `randi_range()` kullanımı.
*   **Gün 7: Uygulama - Toplama Oyunu**
    *   Görev: Rastgele çıkan objeleri toplayıp sinyal ile skoru arttırma.

---

## 5. Hafta: Fizik Motoru ve CharacterBody2D
**Odak:** Platformer Fizikleri

*   **Gün 1: CharacterBody2D Temelleri**
    *   Görev: `velocity`, `move_and_slide()` incelemesi.
*   **Gün 2: Yerçekimi ve Zıplama**
    *   Görev: `is_on_floor()` kontrolü ve yerçekimi ivmesi.
*   **Gün 3: Fizik Katmanları (Layers & Masks)**
    *   Görev: Çarpışma matrisini ayarlama.
*   **Gün 4: RayCast2D**
    *   Görev: Görünmez lazer ile zemin/duvar kontrolü.
*   **Gün 5: Basit Durum Makinesi (State Logic)**
    *   Görev: Enum ile IDLE, RUN, JUMP durumlarını ayırma.
*   **Gün 6: Animasyon (AnimatedSprite2D)**
    *   Görev: Duruma göre animasyon değiştirme.
*   **Gün 7: Uygulama - Mini Platformer**
    *   Görev: Hareket eden, zıplayan, animasyonlu karakter.

---

## 6. Hafta: OOP ve Mimari
**Odak:** Kod Kalitesi ve Modülerlik

*   **Gün 1: Class_name ve Sınıflar**
    *   Görev: Scriptleri global sınıf haline getirme.
*   **Gün 2: Kalıtım (Inheritance)**
    *   Görev: `extends` anahtar kelimesi ile türetme.
*   **Gün 3: Fonksiyon Ezme (Overriding)**
    *   Görev: Alt sınıflarda fonksiyon davranışını değiştirme.
*   **Gün 4: Setters ve Getters**
    *   Görev: Değişken değişince kod çalıştırma mekanizması.
*   **Gün 5: Kaynaklar (Resources)**
    *   Görev: `.tres` dosyaları ile veri tabanı oluşturma (Item Data).
*   **Gün 6: Autoloads (Singletons)**
    *   Görev: Sahne değişse de silinmeyen GameManager yazımı.
*   **Gün 7: Uygulama - Modüler Düşmanlar**
    *   Görev: Aynı temel sınıftan türeyen farklı düşman tipleri.

---

## 7. Hafta: Arayüz (UI) ve Tweening (EKLENDİ)
**Odak:** Görsellik ve Akıcılık

*   **Gün 1: Control Node'ları ve Anchor**
    *   Görev: Duyarlı (Responsive) arayüz tasarımı.
*   **Gün 2: Konteyner Yapıları (VBox, HBox)**
    *   Görev: Otomatik hizalanan menüler.
*   **Gün 3: UI Kodlama**
    *   Görev: Skor ve Can barını kodla güncelleme.
*   **Gün 4: Tween Animasyonları (KRİTİK EKLEME)**
    *   **Görev:** `create_tween()` kullanımı. Kod ile yumuşak geçişler (Can barının yavaşça azalması, butonun büyümesi).
*   **Gün 5: Sahne Geçişleri**
    *   Görev: Ana menü, Oyun, Pause menüsü arası geçiş.
*   **Gün 6: Ses Yönetimi**
    *   Görev: AudioStreamPlayer ve ses veriyolları (Buses).
*   **Gün 7: Uygulama - Tam UI Sistemi**
    *   Görev: Tween ile animasyonlu açılan menüler ve HUD.

---

## 8. Hafta: Tamamlama ve Cila
**Odak:** Ürünleştirme

*   **Gün 1: Hata Ayıklama (Debugging)**
    *   Görev: Breakpoints ve Remote Tree kullanımı.
*   **Gün 2: Refactoring**
    *   Görev: Spagetti kodları temizleme.
*   **Gün 3: Save/Load Sistemi**
    *   Görev: `FileAccess` ile veriyi JSON olarak kaydetme.
*   **Gün 4: Performans Analizi**
    *   Görev: Profiler ile FPS düşüren yerleri bulma.
*   **Gün 5: Export İşlemleri**
    *   Görev: PC ve Web için çıktı alma.
*   **Gün 6: Game Juice (Cila)**
    *   Görev: Tween ile "Screen Shake", Particles2D ile efektler ekleme.
*   **Gün 7: FİNAL PROJE**
    *   **Görev:** Öğrenilen her şeyin kullanıldığı (Menü, Save, Tween, Fizik, OOP) cilalı, bitmiş bir oyun.