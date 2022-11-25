---
title: "[LAWAS] Skor Pribadi Saya untuk Beberapa Anime Musiman, dalam Chart.js"
author: qauland
tags:
   - chart.js
last_modified_at: 2021-07-12
---

Artikel ini **mungkin berat untuk dimuat**. Buka artikel ini di *desktop* untuk mendapatkan tata letak (*layout*) yang bagus.

> Penafian: Ini adalah skor personal saya dan tidak mencerminkan kualitas anime yang sebenarnya. Skor sebelum 1 April 2021 mungkin tidak akurat.

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.8.0/Chart.bundle.js"></script>

<div class="chart-container" style="position: relative; margin: auto; height: 90vh; width: 60vw;">
	<canvas id="canvas"></canvas>
</div>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm';
    
	Chart.defaults.global.defaultFontFamily = 'Inter';
	
	function divideVotes(vote) {
		var dvote = vote;
		return dvote.toLocaleString("id-ID");
	}
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Bokutachi no Remake (Remake Our Life!)",
                    data: [
                    { x: "210702 2030", y: NaN },
                    { x: "210703 2030", y: 7.8 }, //1
                    { x: "210704 2030", y: NaN }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(0,0,175,0.5)',
                    borderColor: 'rgb(0,0,175)',
                    pointBackgroundColor: 'rgb(0,0,175)',
                    pointRadius: 3
                },
                {
                    label: "Cheat Kusushi no Slow Life: Isekai ni Tsukurou Drugstore",
                    data: [
                    { x: "210706 2100", y: NaN },
                    { x: "210707 2100", y: 6.8 }, //1
                    { x: "210708 2100", y: NaN }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(255,255,255,0.5)',
                    borderColor: 'yellow',
                    pointBackgroundColor: 'white',
                    pointRadius: 3
                },
                {
                    label: "Kumo desu ga, Nani ka?",
                    data: [
                    { x: "210107 2030", y: NaN },
                    { x: "210108 2030", y: 7.8 }, //1
                    { x: "210115 2030", y: 7.8 },
                    { x: "210122 2030", y: 7.6 }, //3
                    { x: "210129 2030", y: 7.6 },
                    { x: "210205 2030", y: 7.5 }, //5
                    { x: "210212 2030", y: 7.6 },
                    { x: "210219 2030", y: 7.5 }, //7
                    { x: "210226 2030", y: 7.4 },
                    { x: "210305 2030", y: 7.5 }, //9
                    { x: "210312 2030", y: 7.4 },
                    { x: "210319 2030", y: 7.4 }, //11
                    { x: "210326 2030", y: 7.3 },
                    { x: "210409 2030", y: 7.3 }, //13 - skipped 1 week
                    { x: "210416 2030", y: 7.4 },
                    { x: "210423 2030", y: 7.4 }, //15
                    { x: "210430 2030", y: 7.4 },
                    { x: "210507 2030", y: 7.3 }, //17
                    { x: "210514 2030", y: 7.4 },
                    { x: "210521 2030", y: 7.6 }, //19
                    { x: "210528 2030", y: 7.6 },
                    { x: "210604 2030", y: 7.3 }, //21
                    { x: "210611 2030", y: 7.3 },
                    { x: "210618 2030", y: 7.0 }, //23
                    { x: "210625 2030", y: 7.1 },
                    { x: "210626 2030", y: NaN }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(245,245,245,0.5)',
                    borderColor: 'mediumvioletred',
                    pointBackgroundColor: 'whitesmoke',
                    pointRadius: 3
                },
                {
                    label: "Love Live! Nijigasaki Gakuen School Idol Doukoukai",
                    data: [
                    { x: "201002 2130", y: NaN },
                    { x: "201003 2130", y: 8.5 }, //1
                    { x: "201010 2130", y: 8.6 },
                    { x: "201017 2130", y: 8.6 }, //3
                    { x: "201024 2130", y: 8.5 },
                    { x: "201031 2130", y: 8.4 }, //5
                    { x: "201107 2130", y: 8.5 },
                    { x: "201114 2130", y: 8.5 }, //7
                    { x: "201121 2130", y: 8.4 },
                    { x: "201128 2130", y: 8.3 }, //9
                    { x: "201205 2130", y: 8.1 },
                    { x: "201212 2130", y: 7.9 }, //11
                    { x: "201219 2130", y: 8.0 },
                    { x: "201226 2130", y: 8.1 }, //13
                    { x: "201227 2130", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(0,100,0,0.5)',
                    borderColor: 'darkgreen',
                    pointBackgroundColor: 'darkgreen',
                    pointRadius: 3
                },
                {
                    label: "Majo no Tabitabi",
                    data: [
                    { x: "201001 2000", y: NaN },
                    { x: "201002 2000", y: 8.3 }, //1
                    { x: "201009 2000", y: 8.3 },
                    { x: "201016 2000", y: 8.5 }, //3
                    { x: "201023 2000", y: 8.6 },
                    { x: "201030 2000", y: 8.5 }, //5
                    { x: "201106 2000", y: 8.6 },
                    { x: "201113 2000", y: 8.5 }, //7
                    { x: "201120 2000", y: 8.8 },
                    { x: "201127 2000", y: 8.8 }, //9
                    { x: "201204 2000", y: 8.7 },
                    { x: "201211 2000", y: 8.9 }, //11
                    { x: "201218 2000", y: 9.1 },
                    { x: "201219 2000", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(245,245,245,0.5)',
                    borderColor: 'darkgrey',
                    pointBackgroundColor: 'whitesmoke',
                    pointRadius: 3
                },
                {
                    label: "Maou-jou de Oyasumi",
                    data: [
                    { x: "201005 0100", y: NaN },
                    { x: "201006 0100", y: 8.9 }, //1
                    { x: "201013 0100", y: 9.0 },
                    { x: "201020 0100", y: 9.0 }, //3
                    { x: "201027 0100", y: 8.9 },
                    { x: "201103 0100", y: 8.9 }, //5
                    { x: "201110 0100", y: 9.0 },
                    { x: "201117 0100", y: 9.0 }, //7
                    { x: "201124 0100", y: 9.0 },
                    { x: "201201 0100", y: 9.1 }, //9
                    { x: "201208 0100", y: 9.1 },
                    { x: "201215 0100", y: 9.0 }, //11
                    { x: "201222 0100", y: 9.1 },
                    { x: "201223 0100", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(221,160,221,0.5)',
                    borderColor: 'plum',
                    pointBackgroundColor: 'plum',
                    pointRadius: 3
                },
                {
                    label: "Non Non Biyori Nonstop",
                    data: [
                    { x: "210110 0035", y: NaN },
                    { x: "210111 0050", y: 9.3 }, //1
                    { x: "210118 0035", y: 9.2 },
                    { x: "210125 0035", y: 9.3 }, //3
                    { x: "210201 0035", y: 9.3 },
                    { x: "210208 0035", y: 9.3 }, //5
                    { x: "210215 0035", y: 9.3 },
                    { x: "210222 0035", y: 9.3 }, //7
                    { x: "210301 0035", y: 9.3 },
                    { x: "210308 0035", y: 9.2 }, //9
                    { x: "210315 0035", y: 9.3 },
                    { x: "210322 0035", y: 9.3 }, //11
                    { x: "210329 0035", y: 9.4 },
                    { x: "210330 0035", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(147,112,219,0.5)',
                    borderColor: 'mediumpurple',
                    pointBackgroundColor: 'mediumpurple',
                    pointRadius: 3
                },
                {
                    label: "PUI PUI MOLCAR",
                    data: [
                    { x: "210104 0630", y: NaN },
                    { x: "210105 0630", y: 8.2 }, //1
                    { x: "210112 0630", y: 8.2 },
                    { x: "210119 0630", y: 8.1 }, //3
                    { x: "210126 0630", y: 8.2 },
                    { x: "210202 0630", y: 8.2 }, //5
                    { x: "210209 0630", y: 8.3 },
                    { x: "210216 0630", y: 8.4 }, //7
                    { x: "210223 0630", y: 8.4 },
                    { x: "210303 0630", y: 8.3 }, //9
                    { x: "210310 0630", y: 8.4 },
                    { x: "210317 0630", y: 8.5 }, //11
                    { x: "210324 0630", y: 8.5 },
                    { x: "210323 0630", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(210,180,140,0.5)',
                    borderColor: 'tan',
                    pointBackgroundColor: 'tan',
                    pointRadius: 3
                },
                {
                    label: "Seijo no Maryoku wa Bannou desu",
                    data: [
                    { x: "210405 2230", y: NaN },
                    { x: "210406 2230", y: 8.4 }, //1
                    { x: "210413 2230", y: 8.5 },
                    { x: "210420 2230", y: 8.4 }, //3
                    { x: "210427 2230", y: 8.3 },
                    { x: "210504 2230", y: 8.4 }, //5
                    { x: "210511 2230", y: 8.4 },
                    { x: "210518 2230", y: 8.5 }, //7
                    { x: "210525 2230", y: 8.7 },
                    { x: "210601 2230", y: 8.7 }, //9
                    { x: "210608 2230", y: 8.9 },
                    { x: "210615 2230", y: 8.8 }, //11
                    { x: "210622 2230", y: 8.9 },
                    { x: "210623 2230", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(160,82,45,0.5)',
                    borderColor: 'sienna',
                    pointBackgroundColor: 'sienna',
                    pointRadius: 3
                },
                {
                    label: "Slime Taoshite 300-nen, Shiranai Uchi ni Level Max ni Nattemashita",
                    data: [
                    { x: "210409 2000", y: NaN },
                    { x: "210410 2000", y: 8.5 }, //1
                    { x: "210417 2000", y: 8.5 },
                    { x: "210424 2000", y: 7.7 }, //3
                    { x: "210501 2000", y: 7.5 },
                    { x: "210508 2000", y: 7.6 }, //5
                    { x: "210515 2000", y: 7.3 },
                    { x: "210522 2000", y: 6.8 }, //7
                    { x: "210529 2000", y: 6.3 },
                    { x: "210605 2000", y: 6.3 }, //9
                    { x: "210612 2000", y: 6.3 },
                    { x: "210619 2000", y: 6.3 }, //11
                    { x: "210626 2000", y: 6.4 },
                    { x: "210427 2000", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(125,251,152,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'palegreen',
                    pointRadius: 3
                },
                {
                    label: "Super Cub",
                    data: [
                    { x: "210406 2200", y: NaN },
                    { x: "210407 2200", y: 8.6 }, //1
                    { x: "210414 2200", y: 8.6 },
                    { x: "210421 2200", y: 8.5 }, //3
                    { x: "210428 2200", y: 8.6 },
                    { x: "210505 2200", y: 8.6 }, //5
                    { x: "210512 2200", y: 8.7 },
                    { x: "210519 2200", y: 8.7 }, //7
                    { x: "210526 2200", y: 8.8 },
                    { x: "210602 2200", y: 8.9 }, //9
                    { x: "210609 2200", y: 9.0 },
                    { x: "210616 2200", y: 9.0 }, //11
                    { x: "210624 2200", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(0,0,0,0.5)',
                    borderColor: 'black',
                    pointBackgroundColor: 'black',
                    pointRadius: 3
                },
                {
                    label: "Tantei wa Mou, Shindeiru.",
                    data: [
                    { x: "210703 2030", y: NaN },
                    { x: "210704 2030", y: 7.2 }, //1
                    { x: "210705 2030", y: NaN }
                    ],
                    fill: false,
                    backgroundColor: 'rgba(255,255,255,0.5)',
                    borderColor: 'black',
                    pointBackgroundColor: 'white',
                    pointRadius: 3
                },
                {
                    label: "Yuru Camp△ Season 2",
                    data: [
                    { x: "210106 2200", y: NaN },
                    { x: "210107 2200", y: 8.7 }, //1
                    { x: "210114 2200", y: 8.8 },
                    { x: "210121 2200", y: 8.6 }, //3
                    { x: "210128 2200", y: 8.7 },
                    { x: "210204 2200", y: 8.7 }, //5
                    { x: "210211 2200", y: 8.7 },
                    { x: "210218 2200", y: 8.9 }, //7
                    { x: "210225 2200", y: 9.0 },
                    { x: "210304 2200", y: 9.1 }, //9
                    { x: "210311 2200", y: 9.2 },
                    { x: "210318 2200", y: 9.1 }, //11
                    { x: "210325 2200", y: 9.2 },
                    { x: "210401 2200", y: 9.1 }, //13
                    { x: "210402 2200", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(255,110,147,0.5)',
                    borderColor: 'rgb(255,110,147)',
                    pointBackgroundColor: 'rgb(255,110,147)',
                    pointRadius: 3
                }
            ]
        },
        options: {
            maintainAspectRatio: false,
            responsive: true,
            title:      {
                display: true,
                text:    ['Personal Score Progression for Some Seasonal Anime', '(starting from Autumn 2020)'],
                fontSize: 18
            },
            scales:     {
                xAxes: [{
                    type:       "time",
                    time:       {
                        unit: 'month',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm',
                        	day: 'DD MMM YYYY'
                        },
                        unitStepSize: 3,
                        parser: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Date aired (in WITA)'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Score'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    				return divideVotes(value);
                    	},
                    	min: 6,
                    	max: 10
                    }
                }]
            },
           tooltips: {  //Code taken from https://github.com/chartjs/Chart.js/issues/411#issuecomment-289196968
                enabled: true,

                callbacks: {
                        label: function (tooltipItems, data) {
                        return '"' + data.datasets[tooltipItems.datasetIndex].label + '": ' + tooltipItems.yLabel.toLocaleString("id-ID");
                    }
                }
            },
            elements: {
            	line: {
                	tension: 0 // disables bezier curves
                	
            	}
        	}/*,
        	legend: {
        		labels: {
        			fontSize: 14
        		}
        	}*/
        }
    };

    window.onload = function () {
        var ctx       = document.getElementById("canvas").getContext("2d");
        window.myLine = new Chart(ctx, config);
    }
</script>

<!-- for individual

<div class="chart-container" style="position: relative; margin: auto; height: 400px; width: 550px;">
	<canvas id="canvas"></canvas>
</div>
<script> //Code adapted from https://embed.plnkr.co/JOI1fpgWIS0lvTeLUxUp/
	
    var timeFormat = 'YYMMDD HHmm';
    
	Chart.defaults.global.defaultFontFamily = 'Inter';
	
	function divideVotes(vote) {
		var dvote = vote;
		return dvote.toLocaleString("id-ID");
	}
	
    var config = {
        type:    'line',
        data:    {
            datasets: [
                {
                    label: "Slime Taoshite 300-nen, Shiranai Uchi ni Level Max ni Nattemashita",
                    data: [
                    { x: "210409 2000", y: NaN },
                    { x: "210410 2000", y: 8.5 }, //1
                    { x: "210417 2000", y: 8.5 },
                    { x: "210424 2000", y: 7.7 }, //3
                    { x: "210501 2000", y: 7.5 },
                    { x: "210508 2000", y: 7.6 }, //5
                    { x: "210515 2000", y: 7.3 },
                    { x: "210522 2000", y: 6.8 }, //7
                    { x: "210529 2000", y: 6.3 },
                    { x: "210605 2000", y: 6.3 }, //9
                    { x: "210612 2000", y: 6.3 },
                    { x: "210619 2000", y: 6.3 }, //11
                    { x: "210626 2000", y: 6.4 },
                    { x: "210427 2000", y: NaN }
                    ],
                    fill:  false,
                    backgroundColor: 'rgba(125,251,152,0.5)',
                    borderColor: 'skyblue',
                    pointBackgroundColor: 'palegreen',
                    pointRadius: 3
                }
            ]
        },
        options: {
            maintainAspectRatio: false,
            responsive: true,
            title:      {
                display: true,
                text:    ['Personal Score Progression (Spring 2021)'],
                fontSize: 18
            },
            scales:     {
                xAxes: [{
                    type:       "time",
                    time:       {
                        unit: 'month',
                        displayFormats: {
                        	hour: 'DD MMM HH:mm',
                        	day: 'DD MMM YYYY'
                        },
                        unitStepSize: 1,
                        parser: timeFormat,
                        tooltipFormat: 'DD MMM YYYY HH:mm'
                    },
                    scaleLabel: {
                        display:     true,
                        labelString: 'Date aired (in WITA)'
                    }
                }],
                yAxes: [{
                    scaleLabel: {
                        display:     true,
                        labelString: 'Score'
                    },
                    ticks: {
                    	userCallback: function(value) {
                    				return divideVotes(value);
                    	},
                    	min: 6.0,
                    	max: 10.0
                    }
                }]
            },
           tooltips: {  //Code taken from https://github.com/chartjs/Chart.js/issues/411#issuecomment-289196968
                enabled: true,

                callbacks: {
                        label: function (tooltipItems, data) {
                        return data.datasets[tooltipItems.datasetIndex].label + ': ' + tooltipItems.yLabel.toLocaleString("id-ID");
                    }
                }
            },
            elements: {
            	line: {
                	tension: 0 // disables bezier curves
                	
            	}
        	}/*,
        	legend: {
        		labels: {
        			fontSize: 14
        		}
        	}*/
        }
    };

    window.onload = function () {
        var ctx       = document.getElementById("canvas").getContext("2d");
        window.myLine = new Chart(ctx, config);
    }
</script>
-->
