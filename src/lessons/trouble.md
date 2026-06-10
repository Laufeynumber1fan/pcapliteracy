<h1 id="h-warning"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/raw/refs/heads/gh-pages/pcaps/1-10/trouble.pcapng">Trouble <u>🠇</u></h1></a>
> [!WARNING]  
> This pcap intercepted a phone call!

![](../assets/screenshots/voip1.jpg)

<div class="container">
    <div class="form-row">
        <div class="container">
        <hr>
        <ol>
            <li>
                <p>Which protocol has the most packets in the pcap?</p>
                <ul class="radio-list">
                    <li><label><input type="radio" data-question="PIoV" data-content="0" /> VoIP</label></li>
                    <li><label><input type="radio" data-question="PCT" data-content="0" /> TCP</label></li>
                    <li><label><input type="radio" data-question="PTR" data-content="1" /> RTP</label></li>
                    <li><label><input type="radio" data-question="PTTH" data-content="0" /> HTTP</label></li>
                    <li><label><input type="radio" data-question="PIS" data-content="0" /> SIP</label></li>
                </ul>
            </li>
            <li>
                <p>What's the Caller ID of the person calling James?</p>
                <ul class="radio-list">
                    <li><label><input type="radio" data-question="knaB" data-content="1" /> Bank</label></li>
                    <li><label><input type="radio" data-question="moM" data-content="0" /> Mom</label></li>
                    <li><label><input type="radio" data-question="nwonknU" data-content="0" /> Unknown</label></li>
                    <li><label><input type="radio" data-question="kroW" data-content="0" /> Work</label></li>
                </ul>
            </li>
            <li>
                <p>Listen to the voice call, what kind of attack is James a victim of?</p>
                <ul class="radio-list">
                    <li><label><input type="radio" data-question="kcattA" data-content="0" /> Man In The Middle Attack</label></li>
                    <li><label><input type="radio" data-question="kcattA" data-content="0" /> Replay Attack</label></li>
                    <li><label><input type="radio" data-question="kcattA" data-content="0" /> Phishing Attack</label></li>
                    <li><label><input type="radio" data-question="kcattA" data-content="0" /> Physical Attack</label></li>
                    <li><label><input type="radio" data-question="kcattA" data-content="1" /> Spear-Phishing Attack</label></li>
                </ul>
            </li>
            <li>
                <p>What's the last 4 digits of James' social insurance number?</p>
                <ul class="textbox">
                    <li><input type="text" data-content="8765" data-question="8s7s6s5s" placeholder="Enter the correct answer." class="form-control" />
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