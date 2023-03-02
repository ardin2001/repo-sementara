```
package main

import (
	"fmt"
)

type Bangunan interface {
	luas() int
	keliling() int
}

type Persegi struct {
	sisi int
}

func (p Persegi) luas() int {
	return p.sisi * p.sisi
}
func (p Persegi) keliling() int {
	return 4 * p.sisi
}

type PersegiPanjang struct {
	panjang int
	lebar   int
}

func (pP PersegiPanjang) luas() int {
	return pP.panjang * pP.lebar
}
func (pP PersegiPanjang) keliling() int {
	return 2*pP.panjang + 2*pP.lebar
}

func main() {
	var bangunan Bangunan
	persegi1 := Persegi{
		sisi: 5,
	}
	bangunan = persegi1

	fmt.Println(bangunan.luas())
	fmt.Println(bangunan.keliling())
}
```

Aku nangkepe ngene fik, jadi struct seng wes dibuat objek dan struct tersebut wes ngeinterface interface Bangunan, maka ketika objek persegi1 tak masukno nng interface Bangunan{variabel bangunan) dadi iso njalano method luas karo keliling teko interface


Contoh lain aku nyoba interface
```
package main

import (
	"fmt"
)

type Bangunan interface {
	luas() int
	keliling() int
}

type Persegi struct {
	sisi int
}

func (p Persegi) luas() int {
	return p.sisi * p.sisi
}
func (p Persegi) keliling() int {
	return 4 * p.sisi
}

type PersegiPanjang struct {
	panjang int
	lebar   int
}

func (pP PersegiPanjang) luas() int {
	return pP.panjang * pP.lebar
}
func (pP PersegiPanjang) keliling() int {
	return 2*pP.panjang + 2*pP.lebar
}

func getLuas(bangun Bangunan) int {
	return bangun.luas()
}
func main() {
	persegi1 := Persegi{
		sisi: 5,
	}
	fmt.Println(getLuas(persegi1))
}

```
