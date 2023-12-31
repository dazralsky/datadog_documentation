---
aliases: null
description: Les utilisateurs n'ayant pas accès à la solution RUM peuvent désormais
  prévisualiser des sessions, erreurs et données RUM depuis les résultats de leurs
  tests Browser Synthetic.
further_reading:
- link: https://docs.datadoghq.com/synthetics/browser_tests/
  tag: Documentation
  text: Configurer un test Browser
kind: documentation
title: Explorer des données RUM et Session Replay dans Synthetics
---

## Présentation

<div class="alert alert-info">Si vous n'avez pas accès à la solution Real User Monitoring, vous pouvez prévisualiser des données relatives à RUM, à Session Replay et au suivi des erreurs, ainsi que des données de performance supplémentaires, depuis vos exécutions de test Browser Synthetic.</div>

Les tests Browser Synthetic intègrent le SDK Real User Monitoring. Vous pouvez donc explorer ce qui suit :

- Les données [Session Replay][1] de tous vos tests. Ces informations de contexte supplémentaires viennent compléter les captures d'écran incluses avec chaque étape. Vous avez également accès à des [outils de développement][2].
- Les sessions pertinentes dans le [RUM Explorer][3].
- Les erreurs agrégées pour l'ensemble des étapes, tests et exécutions grâce au [suivi des erreurs][4]. Ces données vous permettent de visualiser uniquement les erreurs ayant un certain impact et de corriger en priorité les problèmes les plus graves.
- Des ressources et informations de durée RUM supplémentaires, avec de nouvelles fonctionnalités de recherche et de surveillance.

## Autoriser les données Synthetic sur les applications RUM

Dans l'enregistrement de votre test Browser, cliquez sur l'option **Collect RUM Data on** au-dessus du bouton **Start Recording**, puis sélectionnez l'application pour laquelle vous souhaitez recueillir des données. Une fois la configuration de votre test et votre enregistrement validée, la solution RUM recueille des données sur les tests et génère des enregistrements de session à partir de vos exécutions de test Browser.

Vous pouvez également cliquer sur `Synthetic Tests Default` et sélectionner une autre application RUM depuis la liste déroulante. Cette application s'affiche dans l'enregistrement de test Browser :

1. Accédez à [**UX Monitoring**> **Settings** > **Integration Settings**][5].
2. Sous **Synthetic Data RUM Applications**, sélectionnez une suggestion d'application RUM par défaut depuis le menu déroulant de l'enregistreur de test Browser.
3. Cliquez sur **Save RUM Preview Settings**.

## Passer de Synthetics au RUM Explorer

Accédez à votre [liste de tests Browser][6], puis cliquez sur une exécution de test.

{{< img src="synthetics/guide/rum_in_synthetics/browser_test_step_side_panel.png" alt="Volet latéral des détails d'une étape de test" style="width:100%;" >}}

Le volet latéral des détails de l'étape s'affiche sous le message `This Synthetic test generated data in Real User Monitoring`. L'ID de session ainsi que le bouton **Go to the View in RUM** figurent en haut du volet.

{{< img src="synthetics/guide/rum_in_synthetics/generated_rum_data.png" alt="Synthetics Explorer" style="width:80%;" >}}

Pour visualiser les erreurs, ressources et données de performance de ce test dans le [RUM Explorer][3], cliquez sur **Go to the View in RUM**. Vous avez également la possibilité de cliquer sur le bouton **Replay Session** ou sur **View all sessions in RUM** pour parcourir les replays disponibles qui ont été enregistrés durant votre test Browser.

## Passer du RUM Explorer à Synthetics

Depuis le RUM Explorer, accédez à votre [liste de sessions][7], puis cliquez sur une session pour laquelle un replay est disponible.

{{< img src="synthetics/guide/rum_in_synthetics/sessions_details_panel.png" alt="Volet latéral des détails d'une session" style="width:100%;" >}}

Le volet latéral s'affiche sous le message `This event was generated by a Synthetic test run`. L'ID de test ainsi que le bouton **View Synthetic Test Result** figurent en haut du volet.

{{< img src="synthetics/guide/rum_in_synthetics/synthetic_test_session.png" alt="Détails d'une session" style="width:80%;" >}}

Pour revenir à la vue Synthetics et aux résultats de votre test, cliquez sur **View Synthetic Test Result**.

## Pour aller plus loin

{{< partial name="whats-next/whats-next.html" >}}

[1]: /fr/real_user_monitoring/session_replay/
[2]: /fr/real_user_monitoring/session_replay/developer_tools/
[3]: /fr/real_user_monitoring/explorer/
[4]: /fr/real_user_monitoring/error_tracking/
[5]: https://app.datadoghq.com/synthetics/settings/integrations
[6]: https://app.datadoghq.com/synthetics/tests?query=type%3A%28browser%29
[7]: https://app.datadoghq.com/rum/explorer