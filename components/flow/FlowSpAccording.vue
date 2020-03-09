<template>
  <div :class="$style.According">
    <div :class="$style.AccordingHead">
      <h3>
        新型コロナ受診相談窓口
        <br />
        <p>
          による相談結果
        </p>
      </h3>
      <dl>
        <dd>新型コロナ外来</dd>
        <dt>受診が必要</dt>
        <dd>と判断された場合</dd>
      </dl>
      <div :class="$style.AccordingHeadBox">
        <p>
          新型コロナ外来(帰国者・接触者外来)
        </p>
        <span>医師による判断</span>
      </div>
    </div>

    <div :class="$style.AccordingExamine">
      <div :class="$style.AccordingExamineItem">
        <a href="#not_required">
          <p>
            検査の必要
            <br />
            <strong>なし</strong>
            <GreenArrow />
          </p>
        </a>
      </div>
      <div :class="$style.AccordingExamineItem">
        <a href="#pcr">
          <p>
            検査の必要
            <br />
            <strong>あり</strong>
            <ArrowIcon />
          </p>
        </a>
      </div>
    </div>

    <div :class="$style.AccordingHead">
      <dl>
        <dt>
          PCR検査
        </dt>
        <dd :class="$style.AccordingHeadSize">
          東京都健康安全研究センター等
        </dd>
      </dl>
      <div :class="$style.AccordingExamine">
        <div :class="$style.AccordingExamineItem">
          <a href="#pcr">
            <p :class="$style.AccordingExamineItemPdg">
              <strong>陰性</strong>
              <GreenArrow />
            </p>
          </a>
        </div>
        <div :class="$style.AccordingExamineItem">
          <a href="#pcr">
            <p :class="$style.AccordingExamineItemPdg">
              <strong>陽性</strong>
              <ArrowIcon />
            </p>
          </a>
        </div>
      </div>
    </div>

    <div :class="[$style.AccordingNot, $style.AccordingHead]">
      <dl>
        <dd>新型コロナ外来</dd>
        <dt>受診が不要</dt>
        <dd>と判断された場合</dd>
      </dl>
      <div :class="$style.AccordingNotFlex">
        <div>
          <HouseIcon />
          <p>
            自宅で
            安静に過ごす
          </p>
        </div>
        <div>
          <HotelIcon />
          <p>
            一般の
            医療機関を受診
          </p>
        </div>
      </div>
      <div　:class="$style.AccordingNotBox">
        <p>
          症状がよくならない場合は
          <br />
          <strong>新型コロナ受診相談窓口</strong>
          <br />
          に相談
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import ArrowIcon from '@/static/flow/arrow_forward-24px.svg'
import GreenArrow from '@/static/flow/arrow_forward_green-24px.svg'
import HouseIcon from '@/static/flow/house-24px.svg'
import HotelIcon from '@/static/flow/apartment-24px.svg'
export default {
  components: { ArrowIcon,HouseIcon,HotelIcon,GreenArrow }
}
</script>

<style module lang="scss">
.According {
  @include card-container();
  text-align: center;
  padding: 30px 20px;
  margin-bottom: 20px;
  font-weight: bold;
  p{
    margin-bottom: 0;
  }
  a{
    text-decoration: none;
    color: $gray-1;
  }
  &Head {
    h3{
      color: $green-1;
      @include font-size(22);
      margin-bottom: 24px;
      @media only screen and (max-width:320px){
        @include font-size(18);
      }
      p{
        @include font-size(18);
      }
    }
    dl{
      @include font-size(16);
      color: $gray-2;
      line-height: 1.4;
      margin-bottom: 8px;
      dt{
        @include font-size(40);
      }
    }
    &Size{
      @include font-size(20);
      width: 54%;
      margin: auto;
      @media only screen and (max-width:320px){
        width: 70%;
      }
    }
    &Box{
      background: $gray-2;
      color: $white;
      border-radius: 4px;
      padding: 12px;
      margin-bottom: 12px;
      p{
        @include font-size(14);
      }
    }
  }
  &Examine{
    display: flex;
    justify-content: center;
    border-bottom: 1px solid $gray-4;
    padding-bottom: 20px;
    margin-bottom: 12px;
    &Item{
      flex-basis: 48%;
      box-shadow: -1px 1px 4px 1px rgba(0, 0, 0, 0.2);
      border-radius: 4px;
      padding: 24px 8px 48px;
      line-height: 1.2;
      p{
        @include font-size(16);
        color: $gray-2;
        position: relative;
        strong{
          @include font-size(24);
        }
        svg{
          position: absolute;
          width: 36px;
          height: 36px;
          top: 100%;
          left: 50%;
          transform: translate(-50%,0) rotate(90deg);
        }
      }
      &Pdg{
        padding-bottom: 10px;
      }
      &:first-child{
        margin-right: 2%;
      }
      &:last-child{
        margin-left: 2%;
        background-color: #FFE200;
      }
    }
  }
  &Not{
    &Flex{
      display: flex;
      margin-bottom: 12px;
      div{
        flex-basis: 48%;
        border:2px solid $gray-4;
        border-radius: 4px;
        padding: 40px 8px 18px;
        line-height: 1.2;
        color: $gray-1;
        position: relative;
        &:first-child{
          margin-right: 2%;
        }
        &:last-child{
          margin-left: 2%;
        }
        svg{
          position: absolute;
          top: 24%;
          left: 50%;
          transform: translate(-50%,-50%);
          width: 32px;
          height: 32px;
        }
        p{
          white-space: pre-line;
          color: $gray-2;
          @include font-size(14);
        }
      }
    }
    &Box{
      border: 2px solid $green-1;
      border-radius: 4px;
      color: $gray-2;
      p{
        padding: 8px 0;
        @include font-size(16);
        @media only screen and (max-width:320px){
          @include font-size(14);
        }
        strong{
          @include font-size(22);
          @media only screen and (max-width:320px){
            @include font-size(16);
          }
        }
      }
    }
  }
}
</style>
