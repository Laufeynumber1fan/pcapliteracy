<h1 id="h-warning"><a href="http://mawi.nezu.wide.ad.jp/mawi/samplepoint-A/1999/199902231911.dump.gz">Silver Lining <u>🠇</u></h1></a>
> [!WARNING]  
> The file is compressed by gzip!

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p>What is the full command for gunzip's help page?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="pizg" data-content="0" /> Get-Help gzip</label></li>
                        <li><label><input type="radio" data-question="h-" data-content="1" /> gunzip -h</label></li>
                        <li><label><input type="radio" data-question="piznug" data-content="0" /> help gunzip</label></li>
                        <li><label><input type="radio" data-question=".piznug" data-content="0" /> There is no help page for gunzip.</label></li>
                    </ul>
                </li>
                <li>
                    <p>What is a <em>possible</em> command to uncompress the downloaded .gz (gunzipped) file?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="zg.pmud.119132209991" data-content="0" /> unzip 199902231911.dump.gz</label></li>
                        <li><label><input type="radio" data-question="zg.pmud.119132209991" data-content="1" /> gunzip 199902231911.dump.gz</label></li>
                        <li><label><input type="radio" data-question="zg.pmud.119132209991" data-content="0" /> gzip -xtract_file 199902231911.dump.gz</label></li>
                        <li><label><input type="radio" data-question="zg.pmud.119132209991" data-content="0" /> gzip &gt; uncompress 199902231911.dump.gz</label></li>
                    </ul>
                </li>
                <li>
                    <p>Are you able to use a pcap analysis tool (ex. tshark) on 199902231911.dump?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=".noisnetxe" data-content="0" /> No, the file must have the .pcap file extension.</label></li>
                        <li><label><input type="radio" data-question=".selif" data-content="0" /> No, pcap analysis tools cannot work with .dump files.</label></li>
                        <li><label><input type="radio" data-question=".seY" data-content="1" /> Yes.</label></li>
                        <li><label><input type="radio" data-question=".noisnetxe" data-content="0" /> Yes, but you have to rename the file to have the .pcap extension.</label></li>
                    </ul>
                </li>
                <li>
                    <p>What is the MD5 hash of 199902231911.dump?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="205747210a7cb6d4003493e7ac994a14" data-question="2s0s5s7s4s7s2s1s0sas7scsbs6sds4s0s0s3s4s9s3ses7sascs9s9s4sas1s4s" placeholder="********************************" maxlength="32" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the destination IP of packet 999?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="6.741.21.902" data-question="6s.s7s4s1s.s2s1s.s9s0s2s" placeholder="***.**.***.*" maxlength="12" class="form-control" />
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