<h1 id="h-caution"><a href="http://mawi.nezu.wide.ad.jp/mawi/ditl/ditl2007/200701090745.dump.gz">Bring Da Ruckus</h1></a>


<details>
    <summary>
        <sub>
            < click me
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-caution">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            tip
        </p>
        <p>
            Use Zeek!
        </p>
    </div>
</details>
  
<sub>^ click me</sub>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p>Using <code>zeek-cut -h</code>, what is the zeek-cut command to change time to UTC format?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="d-" data-content="0" /> cat *.log | zeek-cut -d</label></li>
                        <li><label><input type="radio" data-question="b-" data-content="0" /> zeek-cut -b</label></li>
                        <li><label><input type="radio" data-question="u-" data-content="1" /> zeek-cut -u</label></li>
                        <li><label><input type="radio" data-question="ctu--" data-content="0" /> zeek-cut --utc</label></li>
                    </ul>
                </li>
                <li>
                    <p>What is the most used port by number of connections?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="35" data-question="3s5s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-tip">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            tip
        </p>
        <p>
            <code>zeek-cut</code> source and destination ports and figure out a way to seperate the 2 columns into 2 lines.
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="3">
                <li>
                    <p>What is the 2nd most used TCP port by number of connections?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="531" data-question="5s3s1s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-tip">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            tip
        </p>
        <p>
            <code>zeek-cut</code> port and protocols, grep tcp, and then get rid of the protocols column.
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="4">
                <li>
                    <p>How many unique connections occurred as ICMP traffic?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="289121" data-question="2s8s9s1s2s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many connections occurred on source IP address 211.203.208.87?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="96071" data-question="9s6s0s7s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many connections occurred on destination port 80?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="27994" data-question="2s7s9s9s4s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-tip">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            tip
        </p>
        <p>
            Use <code>^$</code> regex to search exactly for "80"
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="7">
                <li>
                    <p>How many connections occurred on source or destination port 443?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="8691" data-question="8s6s9s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique connections occurred?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="769749" data-question="7s6s9s7s4s9s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-caution">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            BOO!
        </p>
        <p>
            Don't count the beginning lines of zeek headers
        </p>
    </div>
</details>
<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="9">
                <li>
                    <p>How many unique IP addresses belong to the 192.168.0.0/24 subnet?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="51" data-question="5s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique IP addresses can be found?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="609022" data-question="6s0s9s0s2s2s" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>
<details>
    <summary>
        <sub>
        </sub>
    </summary>
    <div class="mdbook-alerts mdbook-alerts-caution">
        <p class="mdbook-alerts-title">
            <span class="mdbook-alerts-icon"></span>
            caution
        </p>
        <p>
            Filter out MAC addresses before you count
        </p>
    </div>
</details>
<br>
    <div id="tg-msg" class="alert" role="alert" style="display: none">
        <span id="tg-correct-questions"></span> Correct! <br /><b>Rating: <span id="tg-score"></span>%</b>
    </div>
    <div class="row">
        <button id="check-questions" class="btn btn-lg btn-success">Check</button>
        <button id="reset-questions" class="btn btn-link">Reset All</button>
    </div>
</div>
<script type="text/javascript">//console.log("Check");
    $(function(){
        $('ul.radio-list,ul.checklist,ul.textbox').each(function(i, el){
            var questionClass = $(this).attr('class');
            $(this).parent().addClass('question-row').addClass(questionClass);
            if (questionClass=='radio-list') {
                $(this).find('input[type="radio"]').attr('name', 'radio-question-' + i);
            }
        });
        function checkQuestion() {
            resetQuestions(true);
            var questions = $('li.question-row');
            var total_questions = questions.length;
            var correct = 0;
            questions.each(function(i, el) {
                var self = $(this);
                // Single Question.
                if (self.hasClass('radio-list')) {
                    //if correct, save data-question as localStorage key
                    //Will use key-value to reenter answers at startup
                    if (self.find('input[type="radio"][data-content="1"]:checked').length == 1) {
                        var checkbox = self.find('input[type="radio"]');
                        var question = String(checkbox.data("question"));
                        localStorage.setItem(question, true);
                        correct += 1;
                    } else {
                        self.addClass('text-danger');
                    }
                }
                // Textbox Question.
                if(self.hasClass('textbox')) {
                    var textbox = self.find('input[type="text"]');
                    var current_text = String(textbox.val()).trim().toLowerCase();
                    var correct_text = String(textbox.data("content")).trim().split("").reverse().join("");
                    var question = String(textbox.data("question"));
                    if(current_text==correct_text.toLowerCase()) {
                        correct += 1;
                        localStorage.setItem(question, textbox.data("content"));
                    } else {
                        self.addClass('text-danger');
                        textbox.parent().find("i.text-correct").html(correct_text);
                    }
                }
                // Multiple selection Questions.
                if(self.hasClass('checklist')) {
                    var total_corrects = self.find('input[type="checkbox"][data-content="1"]').length;
                    var total_incorrects = self.find('input[type="checkbox"][data-content="0"]').length;
                    var correct_selected = self.find('input[type="checkbox"][data-content="1"]:checked').length;
                    var incorrect_selected = self.find('input[type="checkbox"][data-content="0"]:checked').length;
                    var qc = +((correct_selected / total_corrects) - (incorrect_selected/total_incorrects)).toFixed(2);
                    if (qc < 0) {
                        qc = 0;
                    } else if (qc == 1) {
                        var checkbox = self.find('input[type="checkbox"]');
                        var question = String(checkbox.data("question"));
                        localStorage.setItem(question, true);
                    }
                    correct += qc;
                    if (qc == 0) {
                        self.addClass('text-danger');
                    } else if (qc > 0 && qc < 1) {
                        self.addClass('text-warning');
                    }
                }
            });
            showScore(correct, total_questions);
        }
        function showScore(correct, total) {
            var score = (correct / total).toFixed(2) * 100;
            var msgClass = 'alert-danger';
            if (score >= 70) {
                msgClass = 'alert-success';
            } else if (score >= 50) {
                msgClass = 'alert-warning';
            }
            $('#tg-correct-questions').text(correct + ' out of ' + total);
            $('#tg-score').text(score);
            $('#tg-msg').addClass(msgClass).show();
        }
        function resetQuestions(keep) {
            $('li.question-row').removeClass('text-danger').removeClass('text-warning');
            $('i.text-correct').html('');
            $('#tg-msg').removeClass('alert-danger').removeClass('alert-success').removeClass('alert-warning').hide();
            if(keep === true) {
                return;
            }
            $('li.question-row').find('input[type="text"]').val('');
            $('li.question-row').find('input[type="radio"],input[type="checkbox"]').prop('checked', false);
        }
        $('#check-questions').on('click', checkQuestion);
        $('#reset-questions').on('click', resetQuestions);
    });
    //On document ready, reenter saved answers and click the "Check" button
    $(document).ready(function () {
        var previously_answered = false;
        //for loop for localStorage values
        $.each(Object.keys(localStorage), function(i, key) {
            const value = localStorage.getItem(key);
            var questions = $('li.question-row');
            questions.each(function(i, el) {
                var self = $(this);
                if (self.find('[data-question]').data("question") == key) {
                        //answers are recreated
                        if (self.hasClass('radio-list')) {
                        self.find('input[type="radio"][data-content="1"]')[0].checked = true;
                        } else if (self.hasClass('textbox')) {
                        self.find('input[type="text"]')[0].value = value.trim().split("").reverse().join("");
                        } else if (self.hasClass('checklist')) {
                        var checkboxes = self.find('input[type="checkbox"][data-content="1"]');
                        for(var y = 0; y < checkboxes.length; y++){
                            checkboxes[y].checked = true;
                        }
                    }
                    //value saved for any key match, value is used to check if the button needs to be pressed
                    previously_answered = true;
                };
            });
        });
        if (previously_answered) {
                document.getElementById("check-questions").click();
        }
    });
</script>