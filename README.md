class Flervalg:
    def __init__(self, spmtekst, a, b, c, d, riktigsvar):
        self.spmtekst = spmtekst
        self.svaralt = {a: 1, b: 2, c: 3, d: 4}
        self.riktigsvar = int(riktigsvar)

    def sjekk_svar(self):
        svaret = int(input("Hvilket alternativ velger du? "))
        while svaret != self.riktigsvar:
            if svaret > 4:
                print(f"Svaralternativ {svaret} finnes ikke. Velg mellom svaralternativ 1, 2, 3 eller 4.")
                svaret = int(input("Hvilket alternativ velger du? "))
            else:
                print(f"Feil svar, prøv igjen!")
                svaret = int(input("Hvilket alternativ velger du? "))
        return print(f"Riktig! Svaret var {self.riktigsvar}")

    def __str__(self):
        streng = f"{self.spmtekst} \n"
        for key, value in self.svaralt.items():
            streng += f"{value}) {key}\n"
        return streng


if __name__ == "__main__":
    spm1 = "Hvor mange mål har Werner denne sesongen?"
    flervalgs = Flervalg(spm1, "2", "5", "6", "10", 1)
    print(flervalgs)
    flervalgs.sjekk_svar()
    print()
    spm2 = "Hvor mange ganger har Chelsea vunnet Premier League?"
    flervalgs2 = Flervalg(spm2, "10", "6", "14", "0", 2)
    print(flervalgs2)
    flervalgs2.sjekk_svar()
    spm3 = "Hva vil jakob gjør?"
    flervalgs3 = Flervalg(spm3, "hoppe", "sove", "snakke", "spise mat", 1)
    print(flervalgs3)
    flervalgs3.sjekk_svar()
    
