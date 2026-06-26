<h1 id="h-caution"><a href="https://github.com/pan-unit42/wireshark-workshop.git">7th Chamber</h1></a>
 
> [!CAUTION]  
> For this one use `git clone <URL>` on a linux terminal.  
> Can you do the rest on your own?

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p>On workshop-part-05-02.pcap, find the hostname of the webserver hosting the file "invoice_908866.doc"</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="ymra.snd.wgtscnulydtsygrnetin" data-question="ysmsrsas.sssnsds.swsgstssscsnsuslsysdstsssysgsrsnsestsisns" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-02.pcap, what is the MD5 hash of the file "invoice_908866.doc"</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="ddd1e84692177a20dbc79173aeff7753" data-question="dsdsds1ses8s4s6s9s2s1s7s7sas2s0sdsbscs7s9s1s7s3sasesfsfs7s7s5s3s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-02.pcap, find the filename of the PE executable.</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="exe.msager" data-question="esxses.smsssasgsesrs" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-04.pcap, what is the IP address of the SMB server?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="6.1.61.271" data-question="6s.s1s.s6s1s.s2s7s1s" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-04.pcap, what is the SMB2 Tree/Share Name that 172.16.1.103 accessed?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="$CPI\moc.cnisllafelbram.CD-sllaFelbraM\" data-question="$sCsPsIs\smsoscs.scsnsissslslsasfseslsbsrsasms.sCsDs-ssslslsasFseslsbsrsasMs\s" placeholder="\*********************************\***$" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-04.pcap, refer to the "Create Action" of SMB file named "samr", was it created or already existed and opened? Use the wireshark filter "smb2.create.action" to find out.</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=")1(" data-content="1" /> The file existed and was open (1)</label></li>
                        <li><label><input type="radio" data-question="2" data-content="0" /> 2</label></li>
                        <li><label><input type="radio" data-question="EDESREPUS_ELIF" data-content="0" /> FILE_SUPERSEDE</label></li>
                        <li><label><input type="radio" data-question="NEPO_ELIF" data-content="0" /> FILE_OPEN</label></li>
                        <li><label><input type="radio" data-question="ETAERC_ELIF" data-content="0" /> FILE_CREATE</label></li>
                        <li><label><input type="radio" data-question="FI_NEPO_ELIF" data-content="0" /> FILE_OPEN_IF</label></li>
                        <li><label><input type="radio" data-question="ETIRWREVO_ELIF" data-content="0" /> FILE_OVERWRITE</label></li>
                        <li><label><input type="radio" data-question="FI_ETIRWREVO_ELIF" data-content="0" /> FILE_OVERWRITE_IF</label></li>
                        <li><label><input type="radio" data-question="11" data-content="0" /> 11</label></li>
                        <li><label><input type="radio" data-question="x1000x0" data-content="0" /> 0x0001x</label></li>
                        <li><label><input type="radio" data-question=")4(" data-content="0" /> The file did not exist and was created (4)</label></li>
                        <li><label><input type="radio" data-question=")3(" data-content="0" /> The file did not exist (3)</label></li>
                    </ul>
                </li>
                <li>
                    <p>On workshop-part-05-04.pcap, refer to the Session ID regarding the file "samr". What is the account name which accessed "samr"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="neevrednav.ecnerwal" data-question="nsesesvsrsesdsnsasvs.sescsnsesrswsasls" class="form-control" />
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>

> [!CAUTION]  
> The remaining questions uses `workshop-part-05-05.pcap` which contains a scenario in which the host `10.5.7.103` was compromised by an attack.  

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="8">
                <li>
                    <p>Which IP address has received and sent the most TCP PUSH flags?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="301.7.5.01" data-question="3s0s1s.s7s.s5s.s0s1s" placeholder="Enter the correct answer." class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>What is the IP address of the HTTPS web server "cdn.discordapp.com"?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="332.431.951.261" data-question="3s3s2s.s4s3s1s.s9s5s1s.s2s6s1s" placeholder="Enter the correct answer." class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Refer to the first abnormal connection under 79.134.225.19:2555 and investigate for clues. What is the filename that most likely compromised the victim machine?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="exe.noitcerroC-tfiwS" data-question="esxses.snsosistscsesrsrsosCs-stsfsiswsSs" placeholder="Enter the correct answer." class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Which browser contained the victim's amazon.com credentials?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="emorhC" data-question="esmsosrshsCs" placeholder="Enter the correct answer." class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Refer to the other connections under 79.134.225.19:2555, what is the victim's name?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="rebeW otsenrE" data-question="rsesbsesWs sostsssesnsrsEs" placeholder="Enter the correct answer." class="form-control" />
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