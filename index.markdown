<!-- Aufgabe 1 -->
<div id="a1-sortableTrash" class="sortable-code"></div>
<div id="a1-sortable" class="sortable-code"></div>

<div style="clear: both;"></div>

<p>
    <input id="a1-feedbackLink" value="Get Feedback" type="button">
    <input id="a1-newInstanceLink" value="Reset Problem" type="button">
</p>

<script type="text/javascript">
(function () {
    var initial = [
        "for (int i = 0; i < ablagestapel.length; i++)",
        "{",
        "    ablagestapel[i] = new ArrayStack<Karte>();",
        "}",
        "for (int i = 0; i < kaskaden.length; i++)",
        "{",
        "    kaskaden[i] = new ArrayStack<Karte>();",
        "}"
    ].join("\n");

    var parsonsPuzzle = new ParsonsWidget({
        sortableId: "a1-sortable",
        max_wrong_lines: 10,
        grader: ParsonsWidget._graders.LineBasedGrader,
        exec_limit: 2500,
        can_indent: true,
        x_indent: 50,
        lang: "en",
        show_feedback: true,
        python3: true
    });

    parsonsPuzzle.init(initial);
    parsonsPuzzle.shuffleLines();

    $("#a1-newInstanceLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.shuffleLines();
    });

    $("#a1-feedbackLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.getFeedback();
    });
})();
</script>


<!-- Aufgabe 2 -->
<div id="a2-sortableTrash" class="sortable-code"></div>
<div id="a2-sortable" class="sortable-code"></div>

<div style="clear: both;"></div>

<p>
    <input id="a2-feedbackLink" value="Get Feedback" type="button">
    <input id="a2-newInstanceLink" value="Reset Problem" type="button">
</p>

<script type="text/javascript">
(function () {
    var initial = [
        "if (bereich == ZELLEN)",
        "{",
        "    return zellen[index];",
        "}",
        "else if (bereich == ABLAGESTAPEL)",
        "{",
        "    return ablagestapel[index].top();",
        "}",
        "else if (bereich == KASKADEN)",
        "{",
        "    return kaskaden[index].top();",
        "}",
        "return null;"
    ].join("\n");

    var parsonsPuzzle = new ParsonsWidget({
        sortableId: "a2-sortable",
        max_wrong_lines: 10,
        grader: ParsonsWidget._graders.LineBasedGrader,
        exec_limit: 2500,
        can_indent: true,
        x_indent: 50,
        lang: "en",
        show_feedback: true,
        python3: true
    });

    parsonsPuzzle.init(initial);
    parsonsPuzzle.shuffleLines();

    $("#a2-newInstanceLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.shuffleLines();
    });

    $("#a2-feedbackLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.getFeedback();
    });
})();
</script>


<!-- Aufgabe 4 -->
<div id="a4-sortableTrash" class="sortable-code"></div>
<div id="a4-sortable" class="sortable-code"></div>

<div style="clear: both;"></div>

<p>
    <input id="a4-feedbackLink" value="Get Feedback" type="button">
    <input id="a4-newInstanceLink" value="Reset Problem" type="button">
</p>

<script type="text/javascript">
(function () {
    var initial = [
        "Stack<Karte> temp = new ArrayStack<Karte>();",
        "Stack<Karte> s = kaskaden[index];",
        "for (int i = 0; i < n; i++)",
        "{",
        "    temp.push(s.pop());",
        "}",
        "Karte k = s.top();",
        "while (!temp.isEmpty())",
        "{",
        "    s.push(temp.pop());",
        "}",
        "return k;"
    ].join("\n");

    var parsonsPuzzle = new ParsonsWidget({
        sortableId: "a4-sortable",
        max_wrong_lines: 10,
        grader: ParsonsWidget._graders.LineBasedGrader,
        exec_limit: 2500,
        can_indent: true,
        x_indent: 50,
        lang: "en",
        show_feedback: true,
        python3: true
    });

    parsonsPuzzle.init(initial);
    parsonsPuzzle.shuffleLines();

    $("#a4-newInstanceLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.shuffleLines();
    });

    $("#a4-feedbackLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.getFeedback();
    });
})();
</script>


<!-- Aufgabe 5 -->
<div id="a5-sortableTrash" class="sortable-code"></div>
<div id="a5-sortable" class="sortable-code"></div>

<div style="clear: both;"></div>

<p>
    <input id="a5-feedbackLink" value="Get Feedback" type="button">
    <input id="a5-newInstanceLink" value="Reset Problem" type="button">
</p>

<script type="text/javascript">
(function () {
    var initial = [
        "Karte k = null;",
        "if (vonBereich == ZELLEN)",
        "{",
        "    k = zellen[vonIndex];",
        "}",
        "else if (vonBereich == KASKADEN && !kaskaden[vonIndex].isEmpty())",
        "{",
        "    k = kaskaden[vonIndex].top();",
        "}",
        "else",
        "{",
        "    return false;",
        "}",
        "boolean erfolg = false;",
        "if (nachBereich == ZELLEN)",
        "{",
        "    erfolg = (zellen[nachIndex] == null);",
        "    if (erfolg)",
        "    {",
        "        zellen[nachIndex] = k;",
        "    }",
        "}",
        "if (nachBereich == KASKADEN)",
        "{",
        "    if (kaskaden[nachIndex].isEmpty())",
        "    {",
        "        erfolg = true;",
        "    }",
        "    else",
        "    {",
        "        Karte kk = kaskaden[nachIndex].top();",
        "        erfolg = (kk.getWert() == k.getWert() + 1 && kk.istRot() != k.istRot());",
        "    }",
        "    if (erfolg)",
        "    {",
        "        kaskaden[nachIndex].push(k);",
        "    }",
        "}",
        "if (nachBereich == ABLAGESTAPEL)",
        "{",
        "    if (ablagestapel[nachIndex].isEmpty())",
        "    {",
        "        erfolg = (k.getWert() == 1);",
        "    }",
        "    else",
        "    {",
        "        Karte kk = ablagestapel[nachIndex].top();",
        "        erfolg = (kk.getFarbe() == k.getFarbe() && kk.getWert() == k.getWert() - 1);",
        "    }",
        "    if (erfolg)",
        "    {",
        "        ablagestapel[nachIndex].push(k);",
        "    }",
        "}",
        "if (erfolg)",
        "{",
        "    if (vonBereich == ZELLEN)",
        "    {",
        "        zellen[vonIndex] = null;",
        "    }",
        "    else",
        "    {",
        "        kaskaden[vonIndex].pop();",
        "    }",
        "}",
        "return erfolg;"
    ].join("\n");

    var parsonsPuzzle = new ParsonsWidget({
        sortableId: "a5-sortable",
        max_wrong_lines: 10,
        grader: ParsonsWidget._graders.LineBasedGrader,
        exec_limit: 2500,
        can_indent: true,
        x_indent: 50,
        lang: "en",
        show_feedback: true,
        python3: true
    });

    parsonsPuzzle.init(initial);
    parsonsPuzzle.shuffleLines();

    $("#a5-newInstanceLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.shuffleLines();
    });

    $("#a5-feedbackLink").click(function (event) {
        event.preventDefault();
        parsonsPuzzle.getFeedback();
    });
})();
</script>
