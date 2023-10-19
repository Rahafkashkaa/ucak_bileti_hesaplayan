# U-ak-Bileti-Hesablama
Java ile mesafeye ve şartlara göre uçak bileti fiyatı hesaplayan programı yapın. Kullanıcıdan Mesafe (KM), yaşı ve yolculuk tipi (Tek Yön, Gidiş-Dönüş) bilgilerini alın. Mesafe başına ücret 0,10 TL / km olarak alın. İlk olarak uçuşun toplam fiyatını hesaplayın ve sonrasında ki koşullara göre müşteriye aşağıdaki indirimleri uygulayın ;

* Kullanıcıdan alınan değerler geçerli (mesafe ve yaş değerleri pozitif sayı, yolculuk tipi ise 1 veya 2) olmalıdır. Aksi takdirde kullanıcıya "Hatalı Veri Girdiniz !" şeklinde bir uyarı verilmelidir.
- Kişi 12 yaşından küçükse bilet fiyatı üzerinden %50 indirim uygulanır.
- Kişi 12-24 yaşları arasında ise bilet fiyatı üzerinden %10 indirim uygulanır.
- Kişi 65 yaşından büyük ise bilet fiyatı üzerinden %30 indirim uygulanır.
- Kişi "Yolculuk Tipini" gidiş dönüş seçmiş ise bilet fiyatı üzerinden %20 indirim uygulanır.





       import java.util.Scanner;

       public class Main {

          public static void main(String[] args) {

        int km, ago, sec;
        double toplam,yasIndırımsızTutar, kmBasıUcret = 0.10;
        Scanner inp = new Scanner(System.in);

        System.out.print("Yaşınızı giriniz :");
        ago = inp.nextInt();

        System.out.print("Km bilgisi giriniz :");
        km = inp.nextInt();

        System.out.print("Tek yön için 1'i gidiş geliş için 2'yi tıklayın :");
        sec = inp.nextInt();


        if (km > 0 && ago > 0 && sec > 0 && sec < 3) {
            switch (sec) {
                case 1:
                    if (ago < 12) {
                        toplam = km * kmBasıUcret * 0.50;
                        System.out.println("Toplam Tutarı :" + toplam);
                    } else if (ago > 12 && ago < 24) {
                        toplam = km * kmBasıUcret * 0.10;
                        System.out.println("Toplam Tutarı :" + toplam);
                    } else if (ago > 65) {
                        toplam = km * kmBasıUcret * 0.30;
                        System.out.println("Toplam Tutarı :" + toplam);

                    }else { yasIndırımsızTutar=km*kmBasıUcret;
                        System.out.println("İndirimsiz Tutar :" + yasIndırımsızTutar);
                    }
                    break;
                case 2:
                    if (ago < 12) {
                        toplam = km * kmBasıUcret * 0.50 * 0.20;
                        System.out.println("Toplam Tutarı :" + toplam);

                    } else if (ago > 12 && ago < 24) {
                        toplam = km * kmBasıUcret * 0.10 * 0.20;
                        System.out.println("Toplam Tutarı :" + toplam);

                    } else if (ago > 65) {
                        toplam = km * kmBasıUcret * 0.30 * 0.20;
                        System.out.println("Toplam Tutarı :" + toplam);

                    }else { yasIndırımsızTutar=km*kmBasıUcret*0.20;
                        System.out.println("İndirimsiz Tutar :" + yasIndırımsızTutar);
                    }
                    break;
                default:


            }


        } else {
            System.out.println("Hatalı veri girdiniz !!!");
        }
       }
      }
