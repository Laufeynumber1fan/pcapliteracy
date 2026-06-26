<h1 id="h-important"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/raw/refs/heads/gh-pages/material/bewitched.txt">Bewitched</h1></a>
<sup>^^ download me</sup>
> [!IMPORTANT]  
> Regex is a tremendously valuable skill to grasp.

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p><code>cat bewitched.txt | grep -e 123456789</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="87654321" data-content="1" /> 12345678</label></li>
                        <li><label><input type="radio" data-question="9-1" data-content="0" /> Numbers that range from 1-9</label></li>
                        <li><label><input type="radio" data-question="9-1" data-content="0" /> 1-9</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep 426$</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="$624" data-content="0" /> 426$</label></li>
                        <li><label><input type="radio" data-question=""624"" data-content="1" /> Text that ends in "426"</label></li>
                        <li><label><input type="radio" data-question="624" data-content="0" /> 426</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -P wild*</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""dliw"" data-content="0" /> Text that starts with "wild"</label></li>
                        <li><label><input type="radio" data-question=""liw"" data-content="1" /> Text that contains "wil"</label></li>
                        <li><label><input type="radio" data-question=""dliw"" data-content="0" /> Text that does not contain "wild"</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -P 123*</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="321" data-content="0" /> 123</label></li>
                        <li><label><input type="radio" data-question="21" data-content="1" /> 12</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep '192.168'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""861.291"" data-content="0" /> Text that does not contain "192.168"</label></li>
                        <li><label><input type="radio" data-question=""861.291"" data-content="0" /> Text that contains "192.168"</label></li>
                        <li><label><input type="radio" data-question=""861.291"" data-content="1" /> Text that exactly contain "192.168"</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep '8\.8\.'</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=".8.8" data-content="1" /> 8.8.</label></li>
                        <li><label><input type="radio" data-question="8.8.8" data-content="0" /> 8.8.8</label></li>
                        <li><label><input type="radio" data-question=""64648"" data-content="0" /> Text that contains "8.8."</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep 'animal '</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=")ecaps" data-content="1" /> Text that contains "animal " (including the space)</label></li>
                        <li><label><input type="radio" data-question="lamina" data-content="0" /> animal</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -e 'animals?'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="dne" data-content="1" /> Text that contains "animal" and may contain "s" at the end</label></li>
                        <li><label><input type="radio" data-question=""slamina"" data-content="0" /> Text that contains "animals"</label></li>
                        <li><label><input type="radio" data-question="rewsna" data-content="0" /> Text that might have animals or else do not return an answer</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt| grep -e '^204\.'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""402"" data-content="0" /> Text that contains a letter and then "204"</label></li>
                        <li><label><input type="radio" data-question=""64402^"" data-content="0" /> Text that starts with "^204."</label></li>
                        <li><label><input type="radio" data-question="".402"" data-content="1" /> Text that starts with "204."</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt| grep -e '[0-9]'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="9" data-content="0" /> Text that must contain all numbers between 0 to 9</label></li>
                        <li><label><input type="radio" data-question="9" data-content="1" /> A single character that is between 0 to 9</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt| egrep '^10\.0\.2\.2'</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="2.2.0.01" data-content="1" /> 10.0.2.2</label></li>
                        <li><label><input type="radio" data-question=".noisserpxe" data-content="0" /> This is not a valid regex expression.</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep '\/\/\.\?\.\*\.\*abc\.\['</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="[.cba>me/<.>me<.?.//" data-content="1" /> //.?.<em>.</em>abc.[</label></li>
                        <li><label><input type="radio" data-question="1964cba24642464?\64/\/\" data-content="0" /> \/\/.\?.*.*abc.[</label></li>
                        <li><label><input type="radio" data-question="noisserpxe" data-content="0" /> This is not a valid regex expression</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep -v '123'</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""321"" data-content="1" /> Text that does not contain "123"</label></li>
                        <li><label><input type="radio" data-question="321" data-content="0" /> 123</label></li>
                        <li><label><input type="radio" data-question=""321"" data-content="0" /> Text that does not start with "123"</label></li>
                        <li><label><input type="radio" data-question="21" data-content="0" /> 12</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -Pv '^$'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="knalb" data-content="1" /> Lines of text that isn't blank</label></li>
                        <li><label><input type="radio" data-question="noisserpxe" data-content="0" /> This is not a valid regex expression</label></li>
                        <li><label><input type="radio" data-question=""$^"" data-content="0" /> Text that doesn't contain "^$"</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -P '.+'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="+." data-content="0" /> .+</label></li>
                        <li><label><input type="radio" data-question="retcarahc" data-content="1" /> Text that contains one or more of any character</label></li>
                        <li><label><input type="radio" data-question="rebmun" data-content="0" /> Text that contains one or more of a single number</label></li>
                        <li><label><input type="radio" data-question="rettel" data-content="0" /> Text that contains one or more of a single letter</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep '\\\\'</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="noisserpxe" data-content="0" /> This is not a valid regex expression</label></li>
                        <li><label><input type="radio" data-question="29" data-content="1" /> \</label></li>
                        <li><label><input type="radio" data-question="2929" data-content="0" /> \\</label></li>
                        <li><label><input type="radio" data-question="retcarahc" data-content="0" /> Text that contains any alphanumeric character</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep '\/\/\.\?\.\*\.\*abc\.\['</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="[.cba>me/<.>me<.?.//" data-content="1" /> //.?.<em>.</em>abc.[</label></li>
                        <li><label><input type="radio" data-question="1964cba24642464?\64/\/\" data-content="0" /> \/\/.\?.*.*abc.[</label></li>
                        <li><label><input type="radio" data-question="noisserpxe" data-content="0" /> This is not a valid regex expression</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | egrep -v '123'</code><br>
                    What is the output of the egrep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""321"" data-content="1" /> Text that does not contain "123"</label></li>
                        <li><label><input type="radio" data-question="321" data-content="0" /> 123</label></li>
                        <li><label><input type="radio" data-question=""321"" data-content="0" /> Text that does not start with "123"</label></li>
                        <li><label><input type="radio" data-question="21" data-content="0" /> 12</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -Pv '^$'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="knalb" data-content="1" /> Lines of text that isn't blank</label></li>
                        <li><label><input type="radio" data-question="noisserpxe" data-content="0" /> This is not a valid regex expression</label></li>
                        <li><label><input type="radio" data-question=""$^"" data-content="0" /> Text that doesn't contain "^$"</label></li>
                    </ul>
                </li>
                <li>
                    <p><code>cat bewitched.txt | grep -P '.+'</code><br>
                    What is the output of the grep command?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="+." data-content="0" /> .+</label></li>
                        <li><label><input type="radio" data-question="retcarahc" data-content="1" /> Text that contains one or more of any character</label></li>
                        <li><label><input type="radio" data-question="rebmun" data-content="0" /> Text that contains one or more of a single number</label></li>
                        <li><label><input type="radio" data-question="rettel" data-content="0" /> Text that contains one or more of a single letter</label></li>
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