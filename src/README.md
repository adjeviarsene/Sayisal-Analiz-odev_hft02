Pascal Üçgende istenilen satırdaki elemanın bulan algorıthmanın akış dıagramı.

Buradakı yapacağımız işlem sadece  üçgendeki isteceğimiz satırdaki  bulanan bulunan elemaları bulmaktır .
Pascal'ın üçgeni, üçgenin üst elemenları(sayıların) 1 olduğu ve diğer her sayıların sol üst ve sağ üst tarafındaki sayıların toplamı olduğu, üçgen şeklinde şekillendirilmiş sayılardan oluşan bir kalıptır.Genellikle sol tarafın solundaki boş öğelerin ve 1'lerin sağ tarafının sağının 0 olduğu varsayıldığından bahseder. Sadece resmine bakmak daha kolaydır:

1 .satir                                                            1
2 .satir                                                         1      1     
3 .satir                                                       1    2      1
4 .satir                                                   1      3     3        1
5 .satir                                                1      4        6      4     1
6 .satir                                            1        5       10     10     5   1
7.satir                                         1       6        15      20      15     6   1
n .satir                                  *   *  * * * * *   *  *   *    *      *           *
Temel olarak, üçgende herhangi bir değerin ne olduğunu bulmak istiyorsanız, öğeleri sol üst ve sağ üstte toplayabilirsiniz. Dolayısıyla, 5. satırdaki 3. öğeyi istiyorsanız, 4. satırdaki 2. ve 3. öğeleri toplayabilirsiniz, bu 3 + 3 = 6 olacaktır. Ayrıca her satırın ilk ve son öğelerinin 1 olacağını da biliyoruz.
Ayrıca, üçgenin değerlerini saklamanın bir yoluna ihtiyacımız var. Kullandığım yol sadece 2 boyutlu bir diziydi. "Ana dizi", üçgenin her bir satırına, her "alt dizi" ise her satırdaki öğelere karşılık gelir. Üçgenin her satırının, satır numarasıyla aynı sayıda öğeye sahip olduğunu not edebiliriz. İlk satırın 1 öğesi [1], ikinci satırın 2. öğesi [1 1], üçüncü satırın 3. [1 2 1] öğesi vardır vb. Dizinin n'inci satırını bulmak istiyorsak, "ana dizi" n adet alt dizi tutması gerekiyor. Ve her alt dizi, satır numarasıyla aynı uzunluğa sahip olacaktır. Dolayısıyla, alt_dizi_1 uzunluk 1, alt_dizi_2 uzunluk 2, vb.
Artık verilerimizin nasıl yapılandırılacağını bildiğimize göre, geriye kalan tek şey bazı kodları uygulamak ve çalışmasını sağlamaktır. İşte C'de yazdıklarım /src/ klasör bulunmaktadir ve /bin/ kalsör içinde compilable hale (makine dilinde) bir dosya bulunmaktadir.

Temel olarak, üçgende herhangi bir değerin ne olduğunu bulmak istiyorsanız, öğeleri sol üst ve sağ üstte toplayabilirsiniz. Dolayısıyla, 5. satırdaki 3. öğeyi istiyorsanız, 4. satırdaki 2. ve 3. öğeleri toplayabilirsiniz, bu 3 + 3 = 6 olacaktır. Ayrıca her satırın ilk ve son öğelerinin 1 olacağını da biliyoruz.
Ayrıca, üçgenin değerlerini saklamanın bir yoluna ihtiyacımız var. Kullandığım yol sadece 2 boyutlu bir diziydi. "Ana dizi", üçgenin her bir satırına, her "alt dizi" ise her satırdaki öğelere karşılık gelir. Üçgenin her satırının, satır numarasıyla aynı sayıda öğeye sahip olduğunu not edebiliriz. İlk satırın 1 öğesi [1], ikinci satırın 2. öğesi [1 1], üçüncü satırın 3. [1 2 1] öğesi vardır vb. Dizinin n'inci satırını bulmak istiyorsak, "ana dizi" n adet alt dizi tutması gerekiyor. Ve her alt dizi, satır numarasıyla aynı uzunluğa sahip olacaktır. Dolayısıyla, alt_dizi_1 uzunluk 1, alt_dizi_2 uzunluk 2, vb.
Artık verilerimizin nasıl yapılandırılacağını bildiğimize göre, geriye kalan tek şey bazı kodları uygulamak ve çalışmasını sağlamaktır. İşte C'de yazdıklarım /src/ klasör bulunmaktadir ve /bin/ kalsör içinde compilable hale (makine dilinde) bir dosya bulunmaktadir.
Böylece burada kullanıcı yazdırmak istediği satırı girer (number içinde saklanır). myList, her biri setnumber öğelerine sahip olan setnumber alt dizilerine sahiptir. [Not: Bu biraz savurgan ve istenen satır sayısı arttıkça daha israf olur. İdeal olarak, her bir alt dizi, yalnızca gereken minimum boyut olacaktır.

Kullanıcı istenen satırı girdikten sonra, her bir alt dizide hareket etmek için birkaç döngü kullanırız. İlk döngü [for (i = 0…] her bir alt dizide ilerler ve ikinci iç döngü [for (j = 0…] belirli bir alt dizideki her öğe boyunca döngü oluşturur. , alt dizideki ilk veya son öğedeyiz, bu nedenle öğeyi 1 olarak ayarladık. Aksi takdirde, öğeyi önceki alt dizinin öğelerinin toplamına sola ve sağa ayarlayın. Başka bir deyişle, eğer alt dizi 4'te öğe 3'teyiz, öğe 3'ü alt dizi 3'te öğe 2'ye ayarlayacağız + alt dizi 3'te öğe 3.


gcc -g -fstack-protector-strong -std=c99 pascal.c main.c -o sayısalodevone.out