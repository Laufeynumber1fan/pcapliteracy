<h1 id="h-warning"><a href="https://mcfp.felk.cvut.cz/publicDatasets/CTU-Manual-Capture-Attack-1/10.0.0.40.dradis.heartbleed.pcap">Falling Behind</h1></a>
> [!WARNING]
> An attack happened here!

<div class="container">
    <div class="form-row">
        <div class="container">
            <hr>
            <ol>
                <li>
                    <p>Identify the name and version of the web hosting software used by 10.0.0.40.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="61.2.0.01" data-question="6s1s.s2s.s0s.s0s1s" placeholder="**.*.*.**" maxlength="9" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which TCP port is the web server using?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="4003" data-question="4s0s0s3s" placeholder="****" maxlength="4" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the password found in plaintext?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="tset" data-question="tsssests" placeholder="****" maxlength="4" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>How many unique connections occurred between 10.0.0.42 and 10.0.0.40?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="59" data-question="5s9s" placeholder="**" maxlength="2" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
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