<!DOCTYPE html>
 
<html>
<head>
    <script src="https://code.highcharts.com/highcharts.js"></script>
    <script src="https://code.highcharts.com/modules/heatmap.js"></script>
    <script src="https://code.highcharts.com/modules/tilemap.js"></script>
    <script src="https://code.highcharts.com/modules/exporting.js"></script>
    <script src="https://code.highcharts.com/modules/export-data.js"></script>
    <script src="https://code.highcharts.com/modules/accessibility.js"></script>
    
    <figure class="highcharts-figure">
        <div id="container"></div>
        <p class="highcharts-description">
            Mapa exagonal, tambem chamado como coméia de abelha.
            Neste caso irá mostrar a quatidade de alunos que evadiram em 2019, a inferencia será feita pelo ano de matricula.
        </p>
    </figure>
    
</head>
<body>
<script>
 Highcharts.chart('container', {
    chart: {
        type: 'tilemap',
        inverted: true,
        height: '80%'
    },

    accessibility: {
        description: 'Mapa de Evasao',
        screenReaderSection: {
            beforeChartFormat:
                '<h5>{chartTitle}</h5>' +
                '<div>{chartSubtitle}</div>' +
                '<div>{chartLongdesc}</div>' +
                '<div>{viewTableButton}</div>'
        },
        point: {
            valueDescriptionFormat: '{index}. {xDescription}, {point.value}.'
        }
    },

    title: {
        text: 'Mapa dos alunos Evadidos em 2019'
    },

    

    xAxis: {
        visible: false
    },

    yAxis: {
        visible: false
    },

    colorAxis: {
        dataClasses: [{
            from: 0,
            to: 10,
            color: '#F9EDB3',
            name: '< Até 10'
        }, {
            from: 11,
            to: 20,
            color: '#FFC428',
            name: 'De 11 a 20 '
        }, {
            from: 21,
            to: 30,
            color: '#FF7987',
            name: 'De 21 a 30'
        }, {
            from: 31,
            color: '#FF2371',
            name: '> Mais que 30'
        }]
    },

    tooltip: {
        headerFormat: '',
        pointFormat: 'Quantidade de Evasão em: <b> {point.name}</b> is <b>{point.value}</b>'
    },

    plotOptions: {
        series: {
            dataLabels: {
                enabled: true,
                format: '{point.hc-a2}',
                color: '#000000',
                style: {
                    textOutline: false
                }
            }
        }
    },

    series: [{
        name: '',
        data: [{
            'hc-a2': 'CC',
            name: 'Ciêmcias da Computação',
            x: 6,
            y: 3,
            value: 26
        }, {
            'hc-a2': 'MT',
            name: 'Matematica',
            x: 4,
            y: 3,
            value: 20
        }, {
            'hc-a2': 'SI',
            name: 'SISTEMAS DE INFORMAÇÃO',
            x: 5,
            y: 3,
            value: 46
        }, {
            'hc-a2': 'TDS',
            name: 'TECNOLOGIA EM ANALISE/DESENV DE SISTEMAS',
            x: 5,
            y: 4,
            value: 62
        }, {
            'hc-a2': 'TJD',
            name: 'TECNOLOGIA EM JOGOS DIGITAIS',
            x: 5,
            y: 2,
            value: 7
        }]
        
    }]
});

      </script>
</body>
</html>
