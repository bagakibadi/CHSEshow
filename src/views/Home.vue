<template>
  <div class="container">
    <div class="penampungnav">
      <div class="navbar">
        <div class="logo">
          <h2 class="logo-light" style="font-family: sans-serif;" height="35">
            <b style="color: red;">CH</b>
            <b style="color: chocolate;">SE</b>
            <b style="color: dodgerblue;">MI</b>
            <b style="color: lightgreen;">CE</b>
          </h2>
        </div>
        <div class="time">
          <h1>{{time}}</h1>
        </div>
        <div class="info">
          <div class="profile">
            <p>Youre On</p>
            <h1>Devi Dwi Cahyanto</h1>
          </div>
        </div>
      </div>
    </div>
    <div class="section">
      <div class="content">
        <h1>VIRTUAL EVENT CHSE MICE</h1>
        <iframe width="800" height="400" src="https://www.youtube.com/embed/4deVCNJq3qc?autoplay=1" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
    <div class="section2">
      <div class="content2">
        <div class="schedule">
          <div class="judulschedule">
            <h1>Main Stage Schedule</h1>
          </div>
          <div class="contentschedule">
            <div class="judulevent" v-for="i in 20" :key="i.id">
              <h1>Feedback</h1>
              <p>11:50 AM - 12:00 PM</p>
            </div>
          </div>
        </div>
        <div class="day">
          <div class="judulday">
            <h1>Main Stage Day 2</h1>
          </div>
          <div class="paragraf">
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.
               Ut deleniti provident nemo quasi error quibusdam aut molestias
                voluptatem, velit vitae.</p>
          </div>
          <div class="attachment">
            <div class="judulattachment">
              <h1>Attachment</h1>
            </div>
            <div class="centerattachment">
              <i class="fa fa-file"></i>
              <h1>Attachment File is Empty</h1>
              <p>Admin Booth hasn't attached any files yet.</p>
            </div>
          </div>
        </div>
        <div class="chat">
          <div class="judulchat">
            <h1 @click="chat" v-bind:class="{active: isActive == 'chat'}">Chat</h1>
            <h1 @click="feedback" v-bind:class="{active: isActive == 'feedback'}">Feedback</h1>
            <h1 @click="undian" v-bind:class="{active: isActive == 'undian'}">Undian</h1>
          </div>
          <div v-if="code === 1">
            <div class="roomchat">
              <div class="cardchat" v-for="a in 20" :key="a.id">
                <div class="imgchat">
                  <span>io</span>
                </div>
                <div class="infochat">
                  <h1>Firmansyah Adiputra</h1>
                  <div class="isichat">
                    <p>Bu Devi dari mana kok gitu siihhhhashdajsdhj</p>
                  </div>
                </div>
              </div>
            </div>
            <div class="sendmsg">
              <input type="text" placeholder="Coompose Message">
              <i class="fa fa-paper-plane"></i>
            </div>
          </div>
          <div class="feedback" v-if="code === 2" >
            <textarea cols="10" rows="4" placeholder="Feedback"></textarea>
            <button>Send</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
      isActive: 'chat',
      time: null,
      code: 1,
    };
  },
  methods: {
    chat() {
      this.code = 1;
      this.isActive = 'chat';
    },
    feedback() {
      this.code = 2;
      this.isActive = 'feedback';
    },
    undian() {
      this.code = 3;
      this.isActive = 'undian';
    },
    getNow() {
      const today = new Date();
      const time = `${today.getHours()}:${today.getMinutes()}:${today.getSeconds()}`;
      const dateTime = `${time}`;
      this.time = dateTime;
    },
  },
  created() {
    setInterval(this.getNow, 1000);
  },
};
</script>

<style lang="scss" scoped>
.active{
  border-bottom: 3px solid #000 !important;
}
  .container{
    .penampungnav{
      position: relative;
      height: 100px;
      .navbar{
        z-index: 1;
        width: 100%;
        height: 100px;
        background-image: linear-gradient(to right, #6a11cb 0%, #2575fc 100%);
        display: flex;
        align-items: center;
        position: fixed;
        .logo{
          width: 300px;
          height: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          h2{
            b{
              font-size: 30px;
            }
          }
        }
        .time{
          padding: 10px 15px;
          border-radius: 3px;
          background: whitesmoke;
        }
        .judul{
          position: absolute;
          display: flex;
          justify-content: center;
          width: 100%;
          h1{
            font-size: 26px;
            color: white;
          }
        }
        .info{
          display: flex;
          position: absolute;
          right: 0;
          margin-right: 10px;
          .profile{
            margin-right: 5px;
            p{
              color: white;
              text-align: end;
              font-size: 14px;
              margin-bottom: 5px;
            }
            h1{
              color: white;
            }
          }
        }
      }
    }
    .section{
      position: relative;
      width: 100%;
      height: calc(100vh - 100px);
      background: whitesmoke;
      .content{
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 40px;
        box-sizing: border-box;
        h1{
          font-size: 22px;
          margin-bottom: 5px;
        }
        iframe{
          border-radius: 10px;
        }
      }
      .back{
        position: absolute;
        padding: 10px 20px;
        background: blue;
        border-radius: 10px;
        margin-top: 25px;
        margin-left: 40px;
        color: white;
      }
    }
    .section2{
      width: 100%;
      height: calc(100vh - 100px);
      background: #242424 !important;
      display: flex;
      padding: 20px;
      box-sizing: border-box;
      .content2{
        background: whitesmoke;
        width: 100%;
        height: 100%;
        display: flex;
        flex-wrap: wrap;
        border-radius: 8px;
        .schedule{
          width: calc(100% / 3);
          height: 100%;
          border-right: 0.5px solid rgb(201, 186, 186);
          box-sizing: border-box;
          display: flex;
          flex-direction: column;
          padding: 10px 20px;
          .judulschedule{
            width: 100%;
            padding: 25px 20px;
            h1{
              font-size: 22px;
            }
          }
          .contentschedule{
            overflow-y: auto;
            max-height: 360px;
            .judulevent{
              margin: 10px 0;
              border-radius: 8px;
              padding: 20px 30px;
              background: white;
              p{
                font-size: 14px;
              }
            }
          }
        }
        .day{
          width: calc(100% /3);
          height: 100%;
          border-right: 0.5px solid rgb(201, 186, 186);
          box-sizing: border-box;
          padding: 10px 20px;
          .judulday{
            width: 100%;
            padding: 25px 20px;
            h1{
              font-size: 22px;
            }
          }
          .paragraf{
            padding: 0 20px;
            margin-bottom: 30px;
            p{
              font-size: 16px;
              line-height: 25px;
            }
          }
          .attachment{
            padding: 0 20px;
            .judulattachment{
              h1{
                font-size: 20px;
              }
            }
            .centerattachment{
              display: flex;
              flex-direction: column;
              align-items: center;
              i{
                font-size: 80px;
                color: gray;
                margin: 20px;
              }
              h1{
                font-size: 16px;
                margin: 20px 0;
              }
              p{
                font-size: 16px;
              }
            }
          }
        }
        .chat{
          width: calc(100% / 3);
          height: 100%;
          box-sizing: border-box;
          padding: 10px 40px;
          .judulchat{
            padding: 25px 0;
            display: flex;
            h1{
              margin: 0 10px;
              cursor: pointer;
              border-bottom: 3px solid transparent;
            }
            h1:hover{
              box-sizing: border-box;
              border-bottom: 3px solid black;
            }
          }
          .roomchat{
            overflow-y: scroll;
            max-height: 310px;
            .cardchat{
              display: flex;
              margin: 20px 0;
              .imgchat{
                width: 70px;
                display: flex;
                justify-content: center;
                span{
                  width: 45px;
                  height: 45px;
                  background: blue;
                  border-radius: 100%;
                  display: flex;
                  align-items: center;
                  justify-content: center;
                  color: white;
                }
              }
              .infochat{
                h1{
                  margin-bottom: 5px;
                }
                .isichat{
                  background: white;
                  padding: 20px;
                  border-radius: 10px;
                  max-width: 180px;
                  p{
                    font-size: 16px;
                  }
                }
              }
            }
          }
          .feedback{
            textarea{
            box-sizing: border-box;
              width: 100%;
              padding: 15px 15px;
              border-radius: 8px;
              outline: none;
              border: none;
            }
            button{
              width: 100%;
              padding: 10px 0;
              background: blue;
              border: none;
              color: white;
              margin: 10px 0;
              border-radius: 8px;
              outline: none;
              cursor: pointer;
            }
          }
          .sendmsg{
            width: 100%;
            display: flex;
            margin-top: 20px;
            input{
              padding: 15px 20px;
              border-radius: 6px;
              border: none;
              outline: none;
              width: 280px;
            }
            i{
              font-size: 26px;
              padding: 10px;
            }
          }
        }
      }
    }
  }
</style>
