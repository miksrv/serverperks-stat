<!DOCTYPE html>
<html>
    <head>
        <title>Статистика Killing Floor</title>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <link href="css/jquery.dataTables.min.css" rel="stylesheet" type="text/css">
        <link href="css/style.css" rel="stylesheet" type="text/css">
    </head>
    <?php
        $perks = array(
            'SRVetBerserker'    => '128px-Perk_Berserker.png',
            'SRVetCommando'     => '128px-Perk_Commando.png',
            'SRVetDemolitions'  => '128px-Perk_Demolition.png',
            'SRVetFieldMedic'   => '128px-Perk_Medic.png',
            'SRVetFirebug'      => '128px-Perk_Firebug.png',
            'SRVetSharpshooter' => '128px-Perk_SharpShooter.png',
            'SRVetSupportSpec'  => '128px-Perk_Support.png',
        );

        $lang = array(
            'DamageHealedStat'  => 'Лечение команды',
            'WeldingPointsStat' => 'Сварка',
            'ShotgunDamageStat' => 'Поддержка (дробовики)',
            'HeadshotKillsStat' => 'Хедшоты',
            'StalkerKillsStat'  => 'Сталкер (Stalker)',
            'BullpupDamageStat' => 'Коммандос (автоматы)',
            'MeleeDamageStat'   => 'Берсеркер (холодное оружие)',
            'FlameThrowerDamageStat' => 'Поджигатель (огнемет)',
            'SelfHealsStat'          => 'Лечение себя',
            'SoleSurvivorWavesStat'  => 'Единственный выживший',
            'CashDonatedStat'        => 'Передано денег',
            'FeedingKillsStat'       => 'Съеден зомби',
            'BurningCrossbowKillsStat' => 'Убито арбалетом',
            'GibbedFleshpoundsStat'    => 'Казнено отбивальщиков (Fleshpound)',
            'StalkersKilledWithExplosivesStat' => 'Убито сталкеров взрывчаткой',
            'GibbedEnemiesStat' => 'Казнено мутантов',
            'BloatKillsStat'    => 'Толстяк (Bloat)',
            'SirenKillsStat'    => 'Сирена (Siren)',
            'KillsStat'         => 'Убито врагов',
            'ExplosivesDamageStat' => 'Подрывник (взрывчатка)',
            'TotalZedTimeStat'     => 'Время в замедлении',
            'WinsCount'     => 'Игр выиграно',
            'LostsCount'    => 'Игр проиграно',
            'TotalPlayTime' => 'Время в игре',
        );

        $ini_array = parse_ini_file("ServerPerksStat.ini", TRUE);
    ?>
    <body>
        <div class="background">
            <header>
                <h1>Статистика игроков Killing Floor</h1>
                <h5>Просмотр параметров статистики игроков</h5>
            </header>
            <div class="wrapper">
                <div class="tabs">
                    <ul>
                        <li>Общая статистика</li>
                        <li>Специальности</li>
                        <li>Убито врагов</li>
                        <li>Прочее</li>
                    </ul>
                    <div>
                        <div>
                            <br>
                            <table id="table1" class="table table-striped table-bordered">
                                <thead>
                                    <tr>
                                        <th>Игрок</th>
                                        <th><?= $lang['WinsCount'] ?></th>
                                        <th><?= $lang['LostsCount'] ?></th>
                                        <th><?= $lang['TotalPlayTime'] ?></th>
                                        <th><?= $lang['TotalZedTimeStat'] ?></th>
                                        <th><?= $lang['KillsStat'] ?></th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <?php foreach ($ini_array as $key => $val): ?>
                                    <tr>
                                        <td><img src="img/perks/<?= $perks[$val['SelectedVeterancy']] ?>" class="perk" alt="" /><?= $val['PlayerName'] ?></td>
                                        <td><?= $val['WinsCount'] ?></td>
                                        <td><?= $val['LostsCount'] ?></td>
                                        <td><?= sprintf('%02dч. %02dм. %02d с.', $val['TotalPlayTime']/3600, ($val['TotalPlayTime'] % 3600)/60, ($val['TotalPlayTime'] % 3600) % 60); ?></td>
                                        <td><?= sprintf('%02dч. %02dм. %02d с.', $val['TotalZedTimeStat']/3600, ($val['TotalZedTimeStat'] % 3600)/60, ($val['TotalZedTimeStat'] % 3600) % 60); ?></td>
                                        <td><?= $val['KillsStat'] ?></td>
                                    </tr>
                                    <?php endforeach; ?>
                                </tbody>
                            </table>
                            <div class="chart" id="container1"></div>
                            <div class="chart" id="container2"></div>
                        </div>
                        <div>
                            <br>
                            <table id="table2">
                                <thead>
                                    <tr>
                                        <th>Игрок</th>
                                        <th><img src="img/perks/<?= $perks['SRVetFieldMedic'] ?>" class="perk" alt="" />Медик</th>
                                        <th><img src="img/perks/<?= $perks['SRVetSupportSpec'] ?>" class="perk" alt="" />Поддержка</th>
                                        <th><img src="img/perks/<?= $perks['SRVetSharpshooter'] ?>" class="perk" alt="" />Снайпер</th>
                                        <th><img src="img/perks/<?= $perks['SRVetCommando'] ?>" class="perk" alt="" />Коммандос</th>
                                        <th><img src="img/perks/<?= $perks['SRVetBerserker'] ?>" class="perk" alt="" />Берсеркер</th>
                                        <th><img src="img/perks/<?= $perks['SRVetFirebug'] ?>" class="perk" alt="" />Поджигатель</th>
                                        <th><img src="img/perks/<?= $perks['SRVetDemolitions'] ?>" class="perk" alt="" />Подрывник</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <?php foreach ($ini_array as $key => $val): ?>
                                    <tr>
                                        <td><img src="img/perks/<?= $perks[$val['SelectedVeterancy']] ?>" class="perk" alt="" /><?= $val['PlayerName'] ?></td>
                                        <td><?= $val['DamageHealedStat'] ?></td>
                                        <td><?= $val['ShotgunDamageStat'] ?></td>
                                        <td><?= $val['HeadshotKillsStat'] ?></td>
                                        <td><?= $val['BullpupDamageStat'] ?></td>
                                        <td><?= $val['MeleeDamageStat'] ?></td>
                                        <td><?= $val['FlameThrowerDamageStat'] ?></td>
                                        <td><?= $val['ExplosivesDamageStat'] ?></td>
                                        
                                    </tr>
                                    <?php endforeach; ?>
                                </tbody>
                            </table>
                            <div class="chart" id="container3"></div>
                        </div>
                        <div>
                            <br>
                            <table id="table3">
                                <thead>
                                    <tr>
                                        <th>Игрок</th>
                                        <th><?= $lang['BloatKillsStat'] ?></th>
                                        <th><?= $lang['SirenKillsStat'] ?></th>
                                        <th><?= $lang['StalkerKillsStat'] ?></th>
                                        <th><?= $lang['GibbedFleshpoundsStat'] ?></th>
                                        <th><?= $lang['GibbedEnemiesStat'] ?></th>
                                        <th><?= $lang['StalkersKilledWithExplosivesStat'] ?></th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <?php foreach ($ini_array as $key => $val): ?>
                                    <tr>
                                        <td><img src="img/perks/<?= $perks[$val['SelectedVeterancy']] ?>" class="perk" alt="" /><?= $val['PlayerName'] ?></td>
                                        <td><?= $val['BloatKillsStat'] ?></td>
                                        <td><?= $val['SirenKillsStat'] ?></td>
                                        <td><?= $val['StalkerKillsStat'] ?></td>
                                        <td><?= $val['GibbedFleshpoundsStat'] ?></td>
                                        <td><?= $val['GibbedEnemiesStat'] ?></td>
                                        <td><?= $val['StalkersKilledWithExplosivesStat'] ?></td>
                                    </tr>
                                    <?php endforeach; ?>
                                </tbody>
                            </table>
                            <div class="chart" id="container4"></div>
                        </div>
                        <div>
                            <br>
                            <table id="table4" class="table table-striped table-bordered">
                                <thead>
                                    <tr>
                                        <th>Игрок</th>
                                        <th><?= $lang['SelfHealsStat'] ?></th>
                                        <th><?= $lang['WeldingPointsStat'] ?></th>
                                        <th><?= $lang['CashDonatedStat'] ?></th>
                                        <th><?= $lang['SoleSurvivorWavesStat'] ?></th>
                                        <th><?= $lang['FeedingKillsStat'] ?></th>
                                        <th><?= $lang['BurningCrossbowKillsStat'] ?></th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <?php foreach ($ini_array as $key => $val): ?>
                                    <tr>
                                        <td><img src="img/perks/<?= $perks[$val['SelectedVeterancy']] ?>" class="perk" alt="" /><?= $val['PlayerName'] ?></td>
                                        <td><?= $val['SelfHealsStat'] ?> HP</td>
                                        <td><?= $val['WeldingPointsStat'] ?></td>
                                        <td>$<?= $val['CashDonatedStat'] ?></td>
                                        <td><?= $val['SoleSurvivorWavesStat'] ?> (волн)</td>
                                        <td><?= $val['FeedingKillsStat'] ?> (раз)</td>
                                        <td><?= $val['BurningCrossbowKillsStat'] ?></td>
                                    </tr>
                                    <?php endforeach; ?>
                                </tbody>
                            </table>
                        </div>
                    </div>          
                </div>
            </div>
        </div>
        <footer>
            <div class="content">
                <div>Powered by Arduino & PHP\HTML - See on <a href="https://github.com/miksrv/serverperks-stat" title="" target="_blank">Github</a></div>
                <div>Copyright &copy; <a href="http://miksrv.ru" title="" target="_blank">Mishka</a> 2016</div>
            </div>
        </footer>
    </body>
    <script type="text/javascript" src="js/jquery-1.12.2.min.js"></script>
    <script type="text/javascript" src="js/jquery.dataTables.min.js"></script>
    <script type="text/javascript" src="js/highcharts.js"></script>
    <script type="text/javascript" src="js/frontend.js"></script>
    <script type="text/javascript">
        $(function () {
            $('#container1').highcharts({
                chart: {type: 'bar'},
                title: {text: 'Соотношение побед и поражений игроков'},
                xAxis: {
                    categories: ['Побед', 'Поражений'],
                    title: {text: null}
                },
                yAxis: {
                    title: {text: '',align: 'high'},
                    labels: {overflow: 'justify'}
                },
                plotOptions: {
                    bar: {dataLabels: {enabled: true}
                    }
                },
                credits: {enabled: false
                },
                series: [
                <?php foreach ($ini_array as $key => $val): ?>
                    {name: '<?= $val['PlayerName'] ?>', data: [<?= $val['WinsCount'] ?>, <?= $val['LostsCount'] ?>]},
                <?php endforeach; ?>
                ]
            });
    
            $('#container2').highcharts({
                chart: {type: 'bar',},
                title: {text: 'Количество убитых мутантов игроками'},
                xAxis: {
                    categories: [<?php foreach ($ini_array as $key => $val): ?>'<?= $val['PlayerName'] ?>',<?php endforeach; ?>],
                    title: {text: null}
                },
                yAxis: {
                    title: {text: '',align: 'high'},
                    labels: {overflow: 'justify'}
                },
                plotOptions: {
                    bar: {dataLabels: {enabled: true}
                    }
                },
                credits: {enabled: false},
                series: [{name: 'Убитых мутантов',data: [<?php foreach ($ini_array as $key => $val): echo $val['KillsStat'] . ','; endforeach; ?>]}]
            });


            $('#container3').highcharts({
                chart: {type: 'bar',width: '940'},
                title: {text: 'Статистика по специальностям'},
                xAxis: {
                    categories: [
                    <?php foreach ($ini_array as $key => $val): ?>
                        '<?= $val['PlayerName'] ?>',
                    <?php endforeach; ?>
                    ],
                    title: {text: null}
                },
                yAxis: {
                    title: {text: '',align: 'high'},
                    labels: {overflow: 'justify'}
                },
                plotOptions: {
                    bar: {dataLabels: {enabled: true}},
                    series: {stacking: 'normal'}
                },
                credits: {enabled: false},
                series: [
                    {name: 'Медик',data: [<?php foreach ($ini_array as $key => $val): echo $val['DamageHealedStat'] . ','; endforeach; ?>]},
                    {name: 'Поддержка',data: [<?php foreach ($ini_array as $key => $val): echo $val['ShotgunDamageStat'] . ','; endforeach; ?>]},
                    {name: 'Снайпер',data: [<?php foreach ($ini_array as $key => $val): echo $val['HeadshotKillsStat'] . ','; endforeach; ?>]},
                    {name: 'Коммандос',data: [<?php foreach ($ini_array as $key => $val): echo $val['BullpupDamageStat'] . ','; endforeach; ?>]},
                    {name: 'Берсеркер',data: [<?php foreach ($ini_array as $key => $val): echo $val['MeleeDamageStat'] . ','; endforeach; ?>]},
                    {name: 'Поджигатель',data: [<?php foreach ($ini_array as $key => $val): echo $val['FlameThrowerDamageStat'] . ','; endforeach; ?>]},
                    {name: 'Подрывник',data: [<?php foreach ($ini_array as $key => $val): echo $val['ExplosivesDamageStat'] . ','; endforeach; ?>]},
                ]
            });

            $('#container4').highcharts({
                chart: {type: 'bar',width: '940'},
                title: {text: 'Статистика убийств мутантов'},
                xAxis: {
                    categories: [
                    <?php foreach ($ini_array as $key => $val): ?>
                        '<?= $val['PlayerName'] ?>',
                    <?php endforeach; ?>
                    ],
                    title: {text: null}
                },
                yAxis: {
                    labels: {overflow: 'justify'},
                    title: {text: null}
                },
                credits: {enabled: false},
                series: [
                    {name: 'Толстяк (Bloat)',data: [<?php foreach ($ini_array as $key => $val): echo $val['BloatKillsStat'] . ','; endforeach; ?>]},
                    {name: 'Сирена (Siren)',data: [<?php foreach ($ini_array as $key => $val): echo $val['SirenKillsStat'] . ','; endforeach; ?>]},
                    {name: 'Сталкер (Stalker)',data: [<?php foreach ($ini_array as $key => $val): echo $val['StalkerKillsStat'] . ','; endforeach; ?>]},
                    {name: 'Отбивальщик (Fleshpounds)',data: [<?php foreach ($ini_array as $key => $val): echo $val['GibbedFleshpoundsStat'] . ','; endforeach; ?>]},
                ]
            });
        });
    </script>
</html>
