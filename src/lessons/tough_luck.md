<h1 id="h-tip"><a href="https://s3.amazonaws.com/tcpreplay-pcap-files/smallFlows.pcap">Tough Luck</h1></a>

> [!TIP]  
> `-w` is the carving option for both `tshark` and `tcpdump`

> [!CAUTION]
> `-n` makes tcpdump go faster but it omits resolved addresses

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol>
                <li>
                    <p>What is the point of carving pcaps?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question="atad" data-content="0" /> To make it easier for A.I. to analyse data</label></li>
                        <li><label><input type="radio" data-question="ciffart" data-content="0" /> To decode encrypted TLS/SSL network traffic</label></li>
                        <li><label><input type="radio" data-question="erawlam" data-content="0" /> To reveal highly dangerous yet hidden malware</label></li>
                        <li><label><input type="radio" data-question="atad" data-content="1" /> It is a method used by human analysts to help parse large amounts of data</label></li>
                    </ul>
                </li>
                <li>
                    <p>What is wrong with this pcap carving command? <code>tshark -r foo.pcap &gt; carved.pcap</code></p>
                    <ul class="checklist">
                        <li><label><input type="checkbox" data-question="tsol" data-content="1" /> Original data from the pcap is going to be lost</label></li>
                        <li><label><input type="checkbox" data-question="pacp.devrac" data-content="0" /> It is overwriting the original contents of carved.pcap</label></li>
                        <li><label><input type="checkbox" data-question="noitcerider" data-content="0" /> A 2&gt; statement should be added for error redirection</label></li>
                        <li><label><input type="checkbox" data-question="epyt" data-content="1" /> Only string output is being saved so carved.pcap is no longer a pcap file type</label></li>
                    </ul>
                </li>
                    <li>
                    <p>Carve the provided pcap for ONLY tcp packets. What is the new packet amount of the carved pcap?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="80731" data-question="8s0s7s3s1s" placeholder="*****" maxlength="5" class="form-control" />
                    </ul>
                </li>
                    <li>
                    <p>Using the carved pcap, use the filter <code>http</code>. What is the new packet amount of the result?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="1311" data-question="1s3s1s1s" placeholder="****" maxlength="4" class="form-control" />
                    </ul>
                </li>
                    <li>
                    <p>Using the carved pcap, use the filter <code>port 80</code>. What is the new packet amount of the result?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="6038" data-question="6s0s3s8s" placeholder="****" maxlength="4" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Why do you get more HTTP packets from filtering by port instead of protocols?</p>
                    <ul class="radio-list">
                        <li><label><input type="radio" data-question=""PTTH"" data-content="1" /> HTTP data travels in packets but not every packet is labeled as "HTTP"</label></li>
                        <li><label><input type="radio" data-question="locotorp" data-content="0" /> This statement is false and you get more packets by filtering by protocol</label></li>
                        <li><label><input type="radio" data-question="stekcap" data-content="0" /> Filtering by protocols is meant to reveal only the most important packets</label></li>
                        <li><label><input type="radio" data-question="gniretlif" data-content="0" /> Filtering by protocol is an obsolete method that was later replaced by port filtering</label></li>
                    </ul>
                </li>
            </ol>
        </div>
    </div>
</div>

> [!NOTE]  
> You may notice that `tcpdump` is very slow without `-n`.  
> Don't rely on a single tool!

<div class="container">
    <div class="form-row">
        <div class="container">
            <ol start="7">
                <li>
                    <p>Using the original file, carve a new pcap by filtering for IP address 192.168.3.131. What is the new packet amount of the carved pcap?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="87401" data-question="8s7s4s0s1s" placeholder="*****" maxlength="5" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Using the carved pcap for 192.168.3.131, filter for ports 80 and 443. What is the new packet amount of the result?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="5249" data-question="5s2s4s9s" placeholder="****" maxlength="4" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Using the carved pcap for 192.168.3.131, filter for destination port 445 and DNS. What is the new packet amount of the result?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="81" data-question="8s1s" placeholder="**" maxlength="2" class="form-control" />
                    </ul>
                </li>
                <li>
                    <p>Using the carved pcap for 192.168.3.131, filter for ports greater than 1024. What is the new packet amount of the result?</p>
                    <ul class="textbox">
                        <li><input type="text" data-content="92401" data-question="9s2s4s0s1s" placeholder="*****" maxlength="5" class="form-control" />
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
</script