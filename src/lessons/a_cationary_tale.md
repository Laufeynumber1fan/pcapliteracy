<h1 id="h-caution"><a href="https://github.com/Laufeynumber1fan/pcapliteracy/raw/refs/heads/gh-pages/pcaps/1-10/a_cautionary_tale.zip">A Cautionary Tale <u>🠇</u></h1></a>

> [!CAUTION]  
> Oh no! The pcap is SSL encrypted!
<div class="container">
    <div class="form-row">
        <div class="container">
            <hr>
            <ol>
                <li>
                    <p>Which packet started the SSL handshake?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="olleh" data-content="1" /> Packet 1, Client hello</label></li>
                        <li><label><input type="radio" data-question="olleH" data-content="0" /> Packet 3, Server Hello</label></li>
                        <li><label><input type="radio" data-question="etacifitreC" data-content="0" /> Packet 4, Certificate</label></li>
                        <li><label><input type="radio" data-question="tekciT" data-content="0" /> Packet 6, New Session Ticket</label></li>
                    </ul>
                </li>
                <li>
                    <p>Which version of TLS is being used?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="2.1" data-question="2s.s1s" placeholder="*.*" maxlength="3" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Find the public key that was sent by the TLS server (13.107.3.128).</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="a18bb36e28dbd09923e4f2fc07e3a4ddb13237576e68bc205c018b44ee12db69" data-question="as1s8sbsbs3s6ses2s8sdsbsds0s9s9s2s3ses4sfs2sfscs0s7ses3sas4sdsdsbs1s3s2s3s7s5s7s6ses6s8sbscs2s0s5scs0s1s8sbs4s4seses1s2sdsbs6s9s" placeholder="****************************************************************" maxlength="64" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>

> [!TIP]  
> Look up how to decrypt the pcap using the SSLKEYLOGFILE.

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="4">
                <li>
                    <p>What is the User Agent of the decrypted payload in packet 8.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="4102 eciffO tfosorciM" data-question="4s1s0s2s sescsisfsfsOs stsfsosssosrscsisMs" placeholder="********* ****** ****" maxlength="21" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Except for packet 8, which packet also reveals readable data after being decrypted?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="04" data-question="0s4s" placeholder="**" maxlength="2" class="form-control" />
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
