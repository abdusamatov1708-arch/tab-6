# tab-6
BOSH_NARX = 100000

print("--- CHIPTA NARXINI HISOBLASH TIZIMI ---")

yosh = int(input("Yoshingizni kiriting: "))
hafta_oxiri_kiritish = input("Dam olish kunimi? (ha/yo'q): ").strip().lower()
talaba_kiritish = input("Talabamisiz? (ha/yo'q): ").strip().lower()

hafta_oxiri = hafta_oxiri_kiritish == "ha" or hafta_oxiri_kiritish == "yes"
is_student = talaba_kiritish == "ha" or talaba_kiritish == "yes"

if yosh < 0 or yosh > 120:
    print("Xatolik: Bunday yosh mavjud emas!")
    narx = 0
elif yosh >= 0 and yosh <= 6:
    narx = 0
elif yosh >= 7 and yosh <= 17:
    narx = BOSH_NARX * 0.5
elif yosh >= 18 and yosh < 60:
    narx = BOSH_NARX
else:
    narx = BOSH_NARX * 0.7

if hafta_oxiri and narx > 0:
    narx = narx * 1.20

if is_student and narx > 0:
    narx = narx * 0.85

print("-" * 40)
print(f"Chiptaning yakuniy narxi: {narx:,.2f} so'm")
print("-" * 40)
