---
title: Progres dari Real Count KPU pada Pemilihan Presiden 2019
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.13.0/moment.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.bundle.js"></script>

KPU telah memulai proses *real count* Pemilu 2019 sejak tanggal
17 April 2019 lalu. Saya mencoba untuk merekam kemajuan (*progress*)
dari *real count* KPU tersebut.

Lihat [*disclaimer* (sangkalan)](#disclaimer-sangkalan).

Rincian Data
---

| *Last Updated*     | 22 Apr 2019 23:07:05 WITA   |
| *Last Version*[^1] | 22 Apr 2019 23:00:05 WITA   |
| *Last Progress*    | 17,45694% dari 813.350 TPS  |

<!--<p id="countup"></p>-->
<p id="countdown"></p>

<script>
const now = moment();
//let startcount = moment("17 Apr 2019", "DD MMM YYYY");
let endcount = moment("23 May 2019", "DD MMM YYYY");
let diffdown = endcount.diff(now, 'day');
//let diffup = startcount.diff(now, 'day');
let counterdown = document.getElementById('countdown');
counterdown.innerHTML = 'Rekapitulasi suara diperkirakan berakhir dalam ' + diffdown + ' hari.';
//let counterup = document.getElementById('countup');
//counterup.innerHTML = 'Rekapitulasi suara telah berlangsung selama ' + Math.abs(diffup) + ' hari.';
</script>

<!--
| 					 | **Provinsi Sulawesi Selatan** |
|--------------------|-------------------------------|
| *Last Visit*  	 | 20 Apr 2019 17:54:05 WITA	 |
| *Last Version*	 | 20 Apr 2019 17:45:02 WITA	 |
| *Last Progress*    | 5,90021% dari 26.355 TPS      |
-->

[^1]: Versi dari data KPU saat saya terakhir kali memperbarui data.

*Records*
---

[Lihat tabulasi data di Google Spreadsheets.](https://docs.google.com/spreadsheets/d/1_FrbBFEcgaX2rU-BDzjBi-qhuVjWN3oLcfv1lrSBtks/edit?usp=sharing){:target="_blank"}

<canvas id="canvas" width="100%" height="85%"></canvas>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
	function divideVotes(vote) {
		var dvote = vote / 1000000;
		return dvote.toLocaleString("id-ID");
	}
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 1030 03", y: 130952 },
                    { x: "190418 1045 03", y: 141898 },
                    { x: "190418 1230 03", y: 214553 },
                    { x: "190418 1300 03", y: 260891 },
                    { x: "190418 1345 03", y: 296910 },
                    { x: "190418 1430 03", y: 336692 },
                    { x: "190418 1515 03", y: 403079 },
                    { x: "190418 1615 03", y: 482172 },
                    { x: "190418 1700 03", y: 535366 },
                    { x: "190418 1745 03", y: 610654 },
                    { x: "190418 2015 03", y: 723660 },
                    { x: "190418 2145 02", y: 741400 },
                    { x: "190418 2215 03", y: 766633 },
                    { x: "190419 0015 03", y: 945947 },
                    { x: "190419 0500 03", y: 1131661 },
                    { x: "190419 0645 03", y: 1136153 },
                    { x: "190419 0845 02", y: 1158171 },
                    { x: "190419 1100 03", y: 1182353 },
                    { x: "190419 1330 03", y: 1460232 },
                    { x: "190419 1430 03", y: 1652105 },
                    { x: "190419 1630 03", y: 2017709 },
                    { x: "190419 1745 03", y: 2062784 },
                    { x: "190419 1915 02", y: 2308495 },
                    { x: "190419 2015 03", y: 2527064 },
                    { x: "190419 2145 02", y: 2728037 },
                    { x: "190419 2315 02", y: 3201594 },
                    { x: "190420 0015 03", y: 3493887 },
                    { x: "190420 0400 03", y: 3843519 },
                    { x: "190420 0600 03", y: 3855607 },
                    { x: "190420 0700 03", y: 3870392 },
                    { x: "190420 0830 03", y: 3943595 },
                    { x: "190420 1000 02", y: 3966642 },
                    { x: "190420 1245 03", y: 3974811 },
                    { x: "190420 1415 03", y: 3974985 },
                    { x: "190420 1545 03", y: 3974985 },
                    { x: "190420 1745 02", y: 4074791 },
                    { x: "190420 1845 03", y: 4292323 },
                    { x: "190420 2100 03", y: 4654040 },
                    { x: "190421 0545 03", y: 6524078 },
                    { x: "190421 0645 03", y: 6584978 },
                    { x: "190421 1000 03", y: 6817504 },
                    { x: "190421 1315 03", y: 7943509 },
                    { x: "190421 1515 03", y: 8623734 },
                    { x: "190421 1645 03", y: 9061929 },
                    { x: "190421 2030 03", y: 9899149 },
                    { x: "190421 2115 03", y: 9992917 },
                    { x: "190421 2130 03", y: 10003485 },
                    { x: "190421 2300 03", y: 10101749 },
                    { x: "190422 0030 03", y: 10172959 },
                    { x: "190422 0530 02", y: 10939017 },
                    { x: "190422 0645 03", y: 11267315 },
                    { x: "190422 0745 03", y: 11519680 },
                    { x: "190422 1200 03", y: 12596716 },
                    { x: "190422 1345 03", y: 13034658 },
                    { x: "190422 1530 03", y: 13462677 },
                    { x: "190422 1745 05", y: 13868892 },
                    { x: "190422 1915 05", y: 14087278 },
                    { x: "190422 2130 05", y: 14531078 },
                    { x: "190422 2300 05", y: 14809611 }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(253,106,2,0.5)',
                    borderColor: 'orange',
                    pointBackgroundColor: 'orange'
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 1030 03", y: 93168 },
                    { x: "190418 1045 03", y: 98766 },
                    { x: "190418 1230 03", y: 146216 },
                    { x: "190418 1300 03", y: 173138 },
                    { x: "190418 1345 03", y: 202217 },
                    { x: "190418 1430 03", y: 230570 },
                    { x: "190418 1515 03", y: 278317 },
                    { x: "190418 1615 03", y: 344762 },
                    { x: "190418 1700 03", y: 389656 },
                    { x: "190418 1745 03", y: 447461 },
                    { x: "190418 2015 03", y: 534148 },
                    { x: "190418 2145 02", y: 548095 },
                    { x: "190418 2215 03", y: 570742 },
                    { x: "190419 0015 03", y: 722875 },
                    { x: "190419 0500 03", y: 873200 },
                    { x: "190419 0645 03", y: 878541 },
                    { x: "190419 0845 02", y: 897441 },
                    { x: "190419 1100 03", y: 916583 },
                    { x: "190419 1330 03", y: 1157239 },
                    { x: "190419 1430 03", y: 1323415 },
                    { x: "190419 1630 03", y: 1639061 },
                    { x: "190419 1745 03", y: 1678115 },
                    { x: "190419 1915 02", y: 1894876 },
                    { x: "190419 2015 03", y: 2065691 },
                    { x: "190419 2145 02", y: 2242280 },
                    { x: "190419 2315 02", y: 2650827 },
                    { x: "190420 0015 03", y: 2887964 },
                    { x: "190420 0400 03", y: 3186560 },
                    { x: "190420 0600 03", y: 3195689 },
                    { x: "190420 0700 03", y: 3203292 },
                    { x: "190420 0830 03", y: 3237714 },
                    { x: "190420 1000 02", y: 3260762 },
                    { x: "190420 1245 03", y: 3267011 },
                    { x: "190420 1415 03", y: 3267585 },
                    { x: "190420 1545 03", y: 3267585 },
                    { x: "190420 1745 02", y: 3351052 },
                    { x: "190420 1845 03", y: 3526024 },
                    { x: "190420 2100 03", y: 3819116 },
                    { x: "190421 0545 03", y: 5460061 },
                    { x: "190421 0645 03", y: 5536979 },
                    { x: "190421 1000 03", y: 5761443 },
                    { x: "190421 1315 03", y: 6775380 },
                    { x: "190421 1515 03", y: 7306995 },
                    { x: "190421 1645 03", y: 7661540 },
                    { x: "190421 2030 03", y: 8281902 },
                    { x: "190421 2115 03", y: 8347297 },
                    { x: "190421 2130 03", y: 8357386 },
                    { x: "190421 2300 03", y: 8436329 },
                    { x: "190422 0030 03", y: 8515012 },
                    { x: "190422 0530 02", y: 9101848 },
                    { x: "190422 0645 03", y: 9358271 },
                    { x: "190422 0745 03", y: 9522373 },
                    { x: "190422 1200 03", y: 10379989 },
                    { x: "190422 1345 03", y: 10739746 },
                    { x: "190422 1530 03", y: 11041582 },
                    { x: "190422 1745 05", y: 11373470 },
                    { x: "190422 1915 05", y: 11542350 },
                    { x: "190422 2130 05", y: 11878308 },
                    { x: "190422 2300 05", y: 12112135 }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(135,206,235,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'skyblue'
                }
            ]
        },
        options: {
            responsive: true,
            title:      {
                display: true,
                text:    ['Hasil Perekaman Data Real Count KPU 2019', 'Tingkat Nasional'],
                fontSize: 18
            },
            scales:     {
                xAxes: [{
                    type:       "time",
                    time:       {
                        unit: 'hour',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm',
                        	day: 'DD MMM YYYY'
                        },
                        unitStepSize: 16,
                        format: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm:ss'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Tanggal/Versi'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Perolehan Suara'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    			if (value == 0) {
                    				return divideVotes(value);
                    			}
                    		return divideVotes(value) + ' jt';
                    	}
                    }
                }]
            },
           tooltips: {  //Code taken from https://github.com/chartjs/Chart.js/issues/411#issuecomment-289196968
                enabled: true,

                callbacks: {
                    label: function (tooltipItems, data) {
                        return data.datasets[tooltipItems.datasetIndex].label + ': ' + tooltipItems.yLabel.toLocaleString("id-ID") + ' suara';
                    }
                }
            },
            elements: {
            	line: {
                	tension: 0 // disables bezier curves
            	}
        	},
        	legend: {
        		labels: {
        			fontSize: 14
        		}
        	}
        }
    };
//
//    window.onload = function () {
//        var ctx       = document.getElementById("canvas").getContext("2d");
//        window.myLine = new Chart(ctx, config);
//    };
</script>

<!--<canvas id="canvasSulsel" width="100%" height="85%"></canvas>-->
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm ss';
    
	Chart.defaults.global.defaultFontFamily = 'Source Sans Pro';
	
	function divideVotesSulsel(votess) {
		var dvotess = votess / 1000;
		return (dvotess);
	}
	
    var config2 = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Jokowi-Amin",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 2145 02", y: 17843 },
                    { x: "190418 2215 03", y: 18867 },
                    { x: "190419 0015 03", y: 25819 },
                    { x: "190419 0645 03", y: 29000 },
                    { x: "190419 0815 03", y: 29278 },
                    { x: "190419 0845 02", y: 29484 },
                    { x: "190419 1145 03", y: 30421 },
                    { x: "190419 1430 03", y: 51463 },
                    { x: "190419 1630 03", y: 61956 },
                    { x: "190419 1745 03", y: 62893 },
                    { x: "190419 2015 03", y: 79347 },
                    { x: "190419 2145 02", y: 87050 },
                    { x: "190419 2315 02", y: 103409 },
                    { x: "190420 0400 03", y: 128911 },
                    { x: "190420 0700 03", y: 129427 },
                    { x: "190420 0945 03", y: 133382 },
                    { x: "190420 1745 02", y: 135469 }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(253,106,2,0.5)',
                    borderColor: 'orange',
                    pointBackgroundColor: 'orange'
                },
                {
                    label: "Prabowo-Sandi",
                    data: [
                    { x: "190418 1000 00", y: NaN },
                    { x: "190418 2145 02", y: 25168 },
                    { x: "190418 2215 03", y: 26661 },
                    { x: "190419 0015 03", y: 32762 },
                    { x: "190419 0645 03", y: 36827 },
                    { x: "190419 0815 03", y: 37407 },
                    { x: "190419 0845 02", y: 37465 },
                    { x: "190419 1145 03", y: 38441 },
                    { x: "190419 1430 03", y: 65197 },
                    { x: "190419 1630 03", y: 81559 },
                    { x: "190419 1745 03", y: 82478 },
                    { x: "190419 2015 03", y: 100003 },
                    { x: "190419 2145 02", y: 107239 },
                    { x: "190419 2315 02", y: 121477 },
                    { x: "190420 0400 03", y: 146889 },
                    { x: "190420 0700 03", y: 147415 },
                    { x: "190420 0945 03", y: 153093 },
                    { x: "190420 1745 02", y: 155701 }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(135,206,235,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'skyblue'
                }
            ]
        },
        options: {
            responsive: true,
            title:      {
                display: true,
                text:    ['Hasil Perekaman Data Real Count KPU 2019', 'Wilayah Pemilihan Sulawesi Selatan'],
                fontSize: 18
            },
            scales:     {
                xAxes: [{
                    type:       "time",
                    time:       {
                        unit: 'hour',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm'
                        },
                        unitStepSize: 4,
                        format: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm:ss'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Tanggal/Versi'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Perolehan Suara'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    		return divideVotesSulsel(value) + 'rb';
                    	}
                    }
                }]
            },
            elements: {
            	line: {
                	tension: 0 // disables bezier curves
            	}
        	},
        	legend: {
        		labels: {
        			fontSize: 14
        		}
        	}
        }
    };

    window.onload = function () {
        var ctx       = document.getElementById("canvas").getContext("2d");
        window.myLine = new Chart(ctx, config);
        //var ctxSulsel = document.getElementById("canvasSulsel").getContext("2d");
        //window.myLine = new Chart(ctxSulsel, config2);
    }
</script>

*Disclaimer* (Sangkalan)
---

**Situs ini tidak terafiliasi dengan Komisi Pemilihan Umum (KPU)
Republik Indonesia dan pihak-pihak lain dalam bentuk apapun.**

Saya melakukan proses perekaman secara manual dengan mengunjungi
[situs Info Publik Pemilu 2019 milik KPU](<https://pemilu2019.kpu.go.id/#/ppwp/hitung-suara/>){:target="_blank"}
dalam jangka waktu tertentu dan mencatat data di dalamnya.
Sebagai bukti, saya mengambil tangkapan layar saat berkunjung
ke situs KPU dan
[menyimpannya di *mega.nz*](<https://mega.nz/#F!QYBXGSxB!f_a_BKtplMGP6TOFUdAjbw>){:target="_blank"}.

Saya tidak dapat menjamin bahwa saya dapat memperbarui data di
atas secara rutin. *Saya juga tidak dapat menjamin bahwa data di
atas bebas dari kecurangan dan/atau aktivitas peretasan*.

Proses perekaman data dimulai tanggal 18 April 2019 dikarenakan
KPU baru memberikan *raw data* pada tanggal tersebut.

<!--Proses perekaman data untuk provinsi Sulawesi Selatan sedikit
terlambat (18 April 21:53) *karena saya baru pengen ngerekam
pukul segitu*. Khusus untuk provinsi Sulawesi Selatan, tidak ada
tangkapan layar (*screenshot*) yang saya ambil.

Karena tidak ada screenshot yang saya ambil, maka data ini tidak
dapat saya pertanggungjawabkan. Oleh sebab itu, saya memutuskan
untuk menyembunyikannya. Anda (mungkin) bisa melihatnya kembali
dengan menggunakan fitur Inspect Element.-->

Merasa ada kesalahan pada data di atas? Segera
[buat *issue*](<https://github.com/qauland/qauland.github.io/issues/new>){:target="_blank"}
di repositori GitHub situs ini, atau beritahu saya melalui
[Twitter](<https://twitter.com/qauland>){:target="_blank"},
[Facebook](<https://fb.me/qauland>){:target="_blank"},
[Telegram](<https://t.me/qauland>){:target="_blank"}, dan/atau
[Discord](<https://discordapp.com>){:target="_blank"}: qauland#5976.

---Qaulan Ma'ruf Lira

---

